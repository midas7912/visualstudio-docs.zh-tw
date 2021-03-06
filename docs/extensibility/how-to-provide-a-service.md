---
title: 如何： 提供的服務 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- services, providing
ms.assetid: 12bc1f12-47b1-44f6-b8db-862aa88d50d1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2408eace3ecea447c9b49ff17c729e3f4661b5d6
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2018
ms.locfileid: "49942545"
---
# <a name="how-to-provide-a-service"></a>如何： 提供的服務
VSPackage 可以提供其他的 Vspackage 可以使用的服務。 若要提供服務，VSPackage 必須向 Visual Studio 中的服務，然後加入服務。  
  
 <xref:Microsoft.VisualStudio.Shell.Package>類別會實作<xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>和<xref:System.ComponentModel.Design.IServiceContainer>。 <xref:System.ComponentModel.Design.IServiceContainer> 包含隨需提供服務的回呼方法。  
  
 如需有關服務的詳細資訊，請參閱 <<c0> [ 服務 essentials](../extensibility/internals/service-essentials.md) 。  
  
> [!NOTE]
>  即將卸載 VSPackage 時，Visual Studio 會等候直到已傳遞 VSPackage 提供的服務的所有要求。 它不允許這些服務的新要求。 您應該明確地呼叫<xref:Microsoft.VisualStudio.Shell.Interop.IProfferService.RevokeService%2A>卸載時，撤銷服務的方法。  
  
## <a name="implement-a-service"></a>實作服務  
  
1. 建立 VSIX 專案 (**檔案** > **新增** > **專案** > **Visual C#**  > **擴充性** > **VSIX 專案**)。  
  
2. 加入專案中的 VSPackage。 選取專案節點，在**方案總管**，按一下 **新增** > **新項目** > **Visual C# 項目**  > **擴充性** > **Visual Studio 套件**。  
  
3. 若要實作服務，您需要建立三種類型：  
  
   - 描述服務的介面。 許多這些介面是空的也就是說，它們有沒有任何方法。  
  
   - 描述服務介面的介面。 這個介面包含要實作的方法。  
  
   - 實作服務和服務介面的類別。  
  
     下列範例顯示三種類型的基本實作。 服務類別的建構函式必須設定服務提供者。  
  
   ```csharp  
   public class MyService : SMyService, IMyService  
   {  
       private Microsoft.VisualStudio.OLE.Interop.IServiceProvider serviceProvider;  
       private string myString;  
       public MyService(Microsoft.VisualStudio.OLE.Interop.IServiceProvider sp)  
       {  
           Trace.WriteLine(  
                  "Constructing a new instance of MyService");  
           serviceProvider = sp;  
       }  
       public void Hello()  
       {  
           myString = "hello";  
       }  
       public string Goodbye()  
       {  
          return "goodbye";  
       }  
   }  
   public interface SMyService  
   {  
   }  
   public interface IMyService  
   {  
       void Hello();  
       string Goodbye();  
   }  
  
   ```  
  
### <a name="register-a-service"></a>註冊服務  
  
1.  若要註冊的服務，將新增<xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute>來提供服務的 VSPackage。 請看以下範例：  
  
    ```csharp  
    [ProvideService(typeof(SMyService))]  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [Guid(VSPackage1.PackageGuidString)]  
    public sealed class VSPackage1 : Package  
    {. . . }  
    ```  
  
     這個屬性會註冊`SMyService`使用 Visual Studio。  
  
    > [!NOTE]
    >  若要註冊以相同的名稱取代另一個服務的服務，使用<xref:Microsoft.VisualStudio.Shell.ProvideServiceOverrideAttribute>。 請注意在允許的服務只有一個覆寫。  
  
### <a name="add-a-service"></a>新增服務  
  
1.  VSPackage 初始設定式中新增服務以及建立服務的回呼方法。 以下是要對變更<xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A>方法：  
  
    ```csharp  
    protected override void Initialize()  
    {  
        ServiceCreatorCallback callback =new ServiceCreatorCallback(CreateService);  
  
        ((IServiceContainer)this).AddService(typeof(SMyService), callback);  
    . . .  
    }  
    ```  
  
2.  實作回呼方法，應該建立並傳回服務，或如果無法建立，則為 null。  
  
    ```csharp  
    private object CreateService(IServiceContainer container, Type serviceType)  
    {  
        if (typeof(SMyService) == serviceType)  
            return new MyService(this);  
        return null;  
    }  
    ```  
  
    > [!NOTE]
    >  Visual Studio 可以拒絕的要求提供服務。 如果另一個 VSPackage 已提供服務，它可以這麼做。  
  
3.  現在您可以取得服務，並使用它的方法。 下列範例示範使用初始設定式中的服務，但您可以取得任何地方您要使用服務的服務。  
  
    ```csharp  
    protected override void Initialize()  
    {  
        ServiceCreatorCallback callback =new ServiceCreatorCallback(CreateService);  
  
        ((IServiceContainer)this).AddService(typeof(SMyService), callback);  
  
        MyService myService = (MyService) this.GetService(typeof(SMyService));  
        myService.Hello();  
        string helloString = myService.Goodbye();  
  
        base.Initialize();  
    }  
    ```  
  
     值`helloString`應該是"Hello"。  
  
## <a name="see-also"></a>另請參閱  
 [如何： 取得服務](../extensibility/how-to-get-a-service.md)   
 [使用，並提供服務](../extensibility/using-and-providing-services.md)   
 [服務的基本資訊](../extensibility/internals/service-essentials.md)
