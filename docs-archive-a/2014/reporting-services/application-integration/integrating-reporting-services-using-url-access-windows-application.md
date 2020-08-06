---
title: Usar el acceso URL en una aplicación de Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Windows applications [Reporting Services]
- Web Browser controls [Reporting Services]
- Windows Forms [Reporting Services]
- browser controls [Reporting Services]
- URL access [Reporting Services], Windows applications
ms.assetid: a4b222e5-0cbd-409c-92c4-046a674db8ac
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8f8b901481b1d6fcc3cdd8626b43cd3a69174c1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747522"
---
# <a name="using-url-access-in-a-windows-application"></a><span data-ttu-id="576cb-102">Usar el acceso URL en una aplicación para Windows</span><span class="sxs-lookup"><span data-stu-id="576cb-102">Using URL Access in a Windows Application</span></span>
  <span data-ttu-id="576cb-103">Aunque el acceso URL a un servidor de informes se optimiza para un entorno web, también puede utilizar el acceso URL para incrustar informes de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en una aplicación para [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="576cb-103">Although URL access to a report server is optimized for a Web environment, you can also use URL access to embed [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] reports into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application.</span></span> <span data-ttu-id="576cb-104">Sin embargo, el acceso URL que implica formularios Windows Forms todavía requiere que use la tecnología del explorador web.</span><span class="sxs-lookup"><span data-stu-id="576cb-104">However, URL access that involves Windows Forms still requires that you use Web browser technology.</span></span> <span data-ttu-id="576cb-105">Puede utilizar los escenarios de integración siguientes con el acceso URL y los formularios Windows Forms:</span><span class="sxs-lookup"><span data-stu-id="576cb-105">You can use the following integration scenarios with URL access and Windows Forms:</span></span>  
  
-   <span data-ttu-id="576cb-106">Mostrar un informe de una aplicación de formulario Windows Forms iniciando mediante programación un explorador web.</span><span class="sxs-lookup"><span data-stu-id="576cb-106">Display a report from a Windows Form application by starting a Web browser programmatically.</span></span>  
  
-   <span data-ttu-id="576cb-107">Usar el control <xref:System.Windows.Forms.WebBrowser> en un formulario Windows Forms para mostrar un informe.</span><span class="sxs-lookup"><span data-stu-id="576cb-107">Use the <xref:System.Windows.Forms.WebBrowser> control on a Windows Form to display a report.</span></span>  
  
## <a name="starting-internet-explorer-from-a-windows-form"></a><span data-ttu-id="576cb-108">Iniciar Internet Explorer desde un formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="576cb-108">Starting Internet Explorer from a Windows Form</span></span>  
 <span data-ttu-id="576cb-109">Puede utilizar la clase <xref:System.Diagnostics.Process> para tener acceso a un proceso que se está ejecutando en un equipo.</span><span class="sxs-lookup"><span data-stu-id="576cb-109">You can use the <xref:System.Diagnostics.Process> class to access a process that is running on a computer.</span></span> <span data-ttu-id="576cb-110">La <xref:System.Diagnostics.Process> clase es una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] construcción útil para iniciar, detener, controlar y supervisar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="576cb-110">The <xref:System.Diagnostics.Process> class is a useful [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] construct for starting, stopping, controlling, and monitoring applications.</span></span> <span data-ttu-id="576cb-111">Para ver un informe concreto en la base de datos del servidor de informes, puede iniciar el proceso **IExplore** y pasarle la dirección URL al informe.</span><span class="sxs-lookup"><span data-stu-id="576cb-111">To view a specific report in your report server database, you can start the **IExplore** process, passing in the URL to the report.</span></span> <span data-ttu-id="576cb-112">El ejemplo de código siguiente se puede utilizar para iniciar [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer y una dirección URL de un informe concreto cuando el usuario hace clic en un botón de un formulario Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="576cb-112">The following code example can be used to start [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer and pass a specific report URL when the user clicks a button on a Windows Form.</span></span>  
  
```vb  
Private Sub viewReportButton_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles viewReportButton.Click  
   ' Build the URL access string based on values supplied by a user  
   Dim url As String = serverUrlTextBox.Text + "?" & reportPathTextBox.Text & _  
   "&rs:Command=Render" & "&rs:Format=HTML4.0"  
  
   ' If the user does not select the toolbar check box,  
   ' turn the toolbar off in the HTML Viewer  
   If toolbarCheckBox.Checked = False Then  
      url += "&rc:Toolbar=False"  
   End If  
   ' load report in the Web browser  
   Try  
      System.Diagnostics.Process.Start("IExplore", url)  
   Catch  
      MessageBox.Show("The system could not start the specified report using Internet Explorer.", _  
      "An error has occurred", MessageBoxButtons.OK, MessageBoxIcon.Error)  
   End Try  
End Sub 'viewReportButton_Click  
```  
  
```csharp  
// Sample click event for a Button control on a Windows Form  
private void viewReportButton_Click(object sender, System.EventArgs e)  
{  
   // Build the URL access string based on values supplied by a user  
   string url = serverUrlTextBox.Text + "?" + reportPathTextBox.Text +  
      "&rs:Command=Render" + "&rs:Format=HTML4.0";  
  
   // If the user does not check the toolbar check box,  
   // turn the toolbar off in the HTML Viewer  
   if (toolbarCheckBox.Checked == false)  
      url += "&rc:Toolbar=False";  
  
   // load report in the Web browser  
   try  
   {  
      System.Diagnostics.Process.Start("IExplore", url);  
   }  
  
   catch (Exception)  
   {  
      MessageBox.Show(  
         "The system could not open the specified report using Internet Explorer.",   
         "An error has occurred", MessageBoxButtons.OK, MessageBoxIcon.Error);  
   }  
}  
```  
  
## <a name="embedding-a-browser-control-on-a-windows-form"></a><span data-ttu-id="576cb-113">Incrustar un control de explorador en un formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="576cb-113">Embedding a Browser Control on a Windows Form</span></span>  
 <span data-ttu-id="576cb-114">Si no desea ver un informe en un explorador web externo, puede incrustar un explorador web fácilmente como parte de un formulario Windows Forms utilizando el control <xref:System.Windows.Forms.WebBrowser>.</span><span class="sxs-lookup"><span data-stu-id="576cb-114">If you do not want to view your report in an external Web browser, you can embed a Web browser seamlessly as part of your Windows Form using the <xref:System.Windows.Forms.WebBrowser> control.</span></span>  
  
###### <a name="to-add-the-webbrowser-control-to-your-windows-form"></a><span data-ttu-id="576cb-115">Para agregar el control WebBrowser al formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="576cb-115">To add the WebBrowser control to your Windows Form</span></span>  
  
1.  <span data-ttu-id="576cb-116">Cree una nueva aplicación Windows en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="576cb-116">Create a new Windows application in either [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] or [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span>  
  
2.  <span data-ttu-id="576cb-117">Busque el control <xref:System.Windows.Forms.WebBrowser> en el cuadro de diálogo **Cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="576cb-117">Locate the <xref:System.Windows.Forms.WebBrowser> control in the **Toolbox** Dialog Box.</span></span>  
  
     <span data-ttu-id="576cb-118">Si el **cuadro de herramientas** no está visible, puede obtener acceso a él haciendo clic en el elemento del menú **Ver** y seleccionando **Cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="576cb-118">If the **Toolbox** is not visible you can access it by clicking the **View** menu item and selecting **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="576cb-119">Arrastre el control <xref:System.Windows.Forms.WebBrowser> a la superficie de diseño del formulario Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="576cb-119">Drag the <xref:System.Windows.Forms.WebBrowser>control onto the design surface of your Windows Form.</span></span>  
  
     <span data-ttu-id="576cb-120">El control <xref:System.Windows.Forms.WebBrowser> denominado webBrowser1 se agrega al formulario</span><span class="sxs-lookup"><span data-stu-id="576cb-120">The <xref:System.Windows.Forms.WebBrowser>control named webBrowser1 is added to the Form</span></span>  
  
 <span data-ttu-id="576cb-121">Al llamar al método del control <xref:System.Windows.Forms.WebBrowser>**Navigate**, dirige el control a una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="576cb-121">You direct the <xref:System.Windows.Forms.WebBrowser> control to a URL by calling its **Navigate** method.</span></span> <span data-ttu-id="576cb-122">Puede asignar una cadena de acceso URL concreta al control <xref:System.Windows.Forms.WebBrowser> en tiempo de ejecución como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="576cb-122">You can assign a specific URL access string to your <xref:System.Windows.Forms.WebBrowser> control at run time as shown in the following example.</span></span>  
  
```vb  
Dim url As String = "http://localhost/reportserver?/" & _  
                    "AdventureWorks2012 Sample Reports/" & _  
                    "Company Sales&rs:Command=Render"  
WebBrowser1.Navigate(url)  
```  
  
```csharp  
string url = "http://localhost/reportserver?/" +  
             "AdventureWorks2012 Sample Reports/" +  
             "Company Sales&rs:Command=Render";  
webBrowser1.Navigate(url);  
```  
  
## <a name="see-also"></a><span data-ttu-id="576cb-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="576cb-123">See Also</span></span>  
 <span data-ttu-id="576cb-124">[Integración de Reporting Services en aplicaciones](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="576cb-124">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="576cb-125">[Integración de Reporting Services mediante el acceso URL](integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="576cb-125">[Integrating Reporting Services Using URL Access](integrating-reporting-services-using-url-access.md) </span></span>  
 <span data-ttu-id="576cb-126">[Integración de Reporting Services mediante SOAP](integrating-reporting-services-using-soap.md) </span><span class="sxs-lookup"><span data-stu-id="576cb-126">[Integrating Reporting Services Using SOAP](integrating-reporting-services-using-soap.md) </span></span>  
 <span data-ttu-id="576cb-127">[Integrar Reporting Services mediante los controles ReportViewer](integrating-reporting-services-using-reportviewer-controls.md) </span><span class="sxs-lookup"><span data-stu-id="576cb-127">[Integrating Reporting Services Using the ReportViewer Controls](integrating-reporting-services-using-reportviewer-controls.md) </span></span>  
 [<span data-ttu-id="576cb-128">Acceso URL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="576cb-128">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
