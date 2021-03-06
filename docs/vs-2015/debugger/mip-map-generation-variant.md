---
title: Mip-map 產生變異 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b4b3583-0b01-4f5d-aacb-3f96d19111d9
caps.latest.revision: 9
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c567f68abb5b67022bb2decd64ed23e35bf6d5d3
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2018
ms.locfileid: "51723096"
---
# <a name="mip-map-generation-variant"></a>Mip-map 產生變異
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在非呈現目標的紋理上啟用 MIP 對應。  
  
## <a name="interpretation"></a>解譯  
 MIP 對應主要用來透過預先計算較小版本的紋理，來去除處於縮製的紋理中的鋸齒化成品。 雖然這些額外紋理會耗用 GPU 記憶體 (約高於原始紋理的 33%)，但是也更具效率，因為其介面區大部分會放入 GPU 紋理快取中，使其內容會達到較高的使用率。  
  
 針對 3-D 場景，有可儲存其他紋理的記憶體時，建議使用 MIP 對應，因為它們可增加呈現效能和影像品質。  
  
 如果此變異顯現出效能大幅提高，則表示您是使用紋理，而未啟用 MIP 對應，因此未從紋理快取中取得大部分的內容。  
  
## <a name="remarks"></a>備註  
 每次呼叫建立來源紋理的 `ID3D11Device::CreateTexture2D` 時，會強制產生 MIP 對應。 特別是當 `pDesc` 中所傳遞的 D3D11_TEXTUR2D_DESC 物件描述未變更的著色器資源時，會強制產生 MIP 對應；亦即：  
  
- BindFlags 成員只設定 D3D11_BIND_SHADER_RESOURCE 旗標。  
  
- Usage 成員設定為 D3D11_USAGE_DEFAULT 或 D3D11_USAGE_IMMUTABLE。  
  
- CPUAccessFlags 成員設定為 0 (無 CPU 存取)。  
  
- SampleDesc 成員的 Count 成員設定為 1 (無多重取樣消除鋸齒 (MSAA))。  
  
- MipLevels 成員設定為 1 (無現有 MIP 對應)。  
  
  應用程式提供初始資料時，紋理格式必須支援自動產生 MIP 對應 (由 D3D11_FORMAT_SUPPORT_MIP_AUTOGEN 所決定)，除非格式是 BC1、BC2 或 BC3；否則，提供初始資料時，不會修改紋理，也不會產生 MIP 對應。  
  
  如果已自動產生紋理的 MIP 對應，則會在播放期間修改 `ID3D11Device::CreateShaderResourceView` 呼叫，以在紋理取樣期間使用 MIP 鏈結。  
  
## <a name="example"></a>範例  
 **Mip 對應產生**即可重現變體，請使用如下的程式碼：  
  
```  
D3D11_TEXTURE2D_DESC texture_description;  
  
// ...  
  
texture_description.MipLevels = 0; // generate a full mipchain  
  
std::vector<D3D11_SUBRESOURCE_DATA> initial_data(num_mips);  
  
for (auto&& mip_level : initial_data)  
{  
    // fill mip_level with the application-supplied initial data  
}  
  
d3d_device->CreateTexture2D(&texture_description, initial_data.data(), &texture)  
```  
  
 若要建立含有完整 MIP 鏈結的紋理，請將 `D3D11_TEXTURE2D_DESC::MipLevels` 設定為 0。 完整 mip 鏈結中的 mip 層級數目是 floor(log2(n) + 1），其中 n 是紋理的最大維度。  
  
 請記住，當您將初始資料提供給 `CreateTexture2D` 時，必須提供每個 MIP 層級的 D3D11_SUBRESOURCE_DATA 物件。  
  
> [!NOTE]
>  如果您想要提供您的 MIP 層級內容，而不是自動產生該內容，則必須使用可支援經過 MIP 對應之紋理的影像編輯器來建立紋理，然後載入檔案，並將 MIP 層級傳遞給 `CreateTexture2D`。  
  
## <a name="see-also"></a>另請參閱  
 [二分之一/四分之一紋理維度變化](../debugger/half-quarter-texture-dimensions-variant.md)



