---
title: 'Lección 1: crear el proyecto de Visual Studio de esquema RDL | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f420509c-51aa-4170-8c25-64c2954f4bb9
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: a8411e3f0458ccda8c291d5c86a4467bb051a263
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743721"
---
# <a name="lesson-1-create-the-rdl-schema-visual-studio-project"></a><span data-ttu-id="963dc-102">Lección 1: Creación del proyecto de Visual Studio Esquema RDL</span><span class="sxs-lookup"><span data-stu-id="963dc-102">Lesson 1: Create the RDL Schema Visual Studio Project</span></span>
  <span data-ttu-id="963dc-103">Para este tutorial creará una aplicación de consola sencilla.</span><span class="sxs-lookup"><span data-stu-id="963dc-103">For this tutorial, you will create a simple console application.</span></span> <span data-ttu-id="963dc-104">En este tutorial se da por supuesto que está desarrollando en [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="963dc-104">This tutorial assumes you are developing in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="963dc-105">Al tener acceso al servicio web del servidor de informes que se ejecuta en [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] con Advanced Services, debe agregar "?SQLExpress" a la ruta de acceso de "ReportServer".</span><span class="sxs-lookup"><span data-stu-id="963dc-105">When accessing the Report Server Web service running on [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services, you must append "_SQLExpress" to the "ReportServer" path.</span></span> <span data-ttu-id="963dc-106">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="963dc-106">For example:</span></span>  
>   
>  `http://myserver/reportserver_sqlexpress/reportservice2010.asmx"`  
  
### <a name="to-create-the-web-service-proxy"></a><span data-ttu-id="963dc-107">Crear el proxy del servicio web</span><span class="sxs-lookup"><span data-stu-id="963dc-107">To create the web service proxy</span></span>  
  
1.  <span data-ttu-id="963dc-108">En el menú **Inicio** , seleccione **todos los programas**, Microsoft Visual Studio, **Visual Studio Tools**y, por último, **símbolo del sistema de Visual Studio 2010**.</span><span class="sxs-lookup"><span data-stu-id="963dc-108">From the **Start** menu, select **All Programs**, then Microsoft Visual Studio, then **Visual Studio Tools**, and then **Visual Studio 2010 Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="963dc-109">En la ventana del símbolo del sistema, ejecute el siguiente comando si está utilizando C#:</span><span class="sxs-lookup"><span data-stu-id="963dc-109">In the command prompt window, run the following command if you are using C#:</span></span>  
  
    ```  
    wsdl /language:CS /n:"ReportService2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="963dc-110">Si usa Visual Basic, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="963dc-110">If you are using Visual Basic, then run the following command:</span></span>  
  
    ```  
    wsdl /language:VB /n:"ReportService2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="963dc-111">Este comando genera un archivo .cs o .vb.</span><span class="sxs-lookup"><span data-stu-id="963dc-111">This command generates a .cs or .vb file.</span></span> <span data-ttu-id="963dc-112">Agregará este archivo a su aplicación.</span><span class="sxs-lookup"><span data-stu-id="963dc-112">You will add this file to your application.</span></span>  
  
### <a name="to-create-a-console-application"></a><span data-ttu-id="963dc-113">Crear una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="963dc-113">To create a console application</span></span>  
  
1.  <span data-ttu-id="963dc-114">En el menú **archivo** , seleccione **nuevo**y, a continuación, haga clic en **proyecto** para abrir el cuadro de diálogo **nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="963dc-114">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="963dc-115">En el panel izquierdo, en **plantillas instaladas**, haga clic en **Visual Basic** o en el nodo **Visual C#** y seleccione una categoría de tipos de proyecto en la lista expandida.</span><span class="sxs-lookup"><span data-stu-id="963dc-115">In the left pane, under **Installed Templates**, click either **Visual Basic** or the **Visual C#** node, and select a category of project types from the expanded list.</span></span>  
  
3.  <span data-ttu-id="963dc-116">Elija el tipo de proyecto **aplicación de consola** .</span><span class="sxs-lookup"><span data-stu-id="963dc-116">Choose the **Console Application** project type.</span></span>  
  
4.  <span data-ttu-id="963dc-117">En el cuadro **nombre** , escriba un nombre para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="963dc-117">In the **Name** box, enter a name for your project.</span></span> <span data-ttu-id="963dc-118">Escriba el nombre `SampleRDLSchema` .</span><span class="sxs-lookup"><span data-stu-id="963dc-118">Type the name `SampleRDLSchema`.</span></span>  
  
5.  <span data-ttu-id="963dc-119">En el cuadro **Ubicación** , escriba la ruta de acceso donde desea guardar el proyecto o haga clic en **examinar** para navegar hasta la carpeta.</span><span class="sxs-lookup"><span data-stu-id="963dc-119">In the **Location** box, type the path where you want to save your project, or click **Browse** to navigate to the folder.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="963dc-120">En Explorador de soluciones se muestra una vista contraída del proyecto.</span><span class="sxs-lookup"><span data-stu-id="963dc-120">A collapsed view of your project appears in Solution Explorer.</span></span>  
  
7.  <span data-ttu-id="963dc-121">En el menú **Proyecto** , haga clic en **Agregar elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="963dc-121">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
8.  <span data-ttu-id="963dc-122">Navegue hasta la ubicación del archivo. cs o. VB que ha generado, seleccione el archivo y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="963dc-122">Navigate to the location for the .cs or .vb file you generated, then select the file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="963dc-123">También necesitará agregar una referencia al espacio de nombres <xref:System.Web.Services> para que su referencia web funcione.</span><span class="sxs-lookup"><span data-stu-id="963dc-123">You will also need to add a reference to the <xref:System.Web.Services> namespace for your Web reference to work.</span></span>  
  
9. <span data-ttu-id="963dc-124">En el menú Proyecto, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="963dc-124">On the Project menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="963dc-125">En el cuadro de diálogo **Agregar referencia** , en la pestaña **.net** , seleccione **System. Web. Services**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="963dc-125">In the **Add Reference** dialog box, in the **.NET** tab, select **System.Web.Services**, then click **OK**.</span></span>  
  
     <span data-ttu-id="963dc-126">Para obtener más información sobre cómo conectarse al servicio Web del servidor de informes, vea [compilar aplicaciones con el servicio Web y el .NET Framework](../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md).</span><span class="sxs-lookup"><span data-stu-id="963dc-126">For more information about how to connect to the Report Server Web service, see [Building Applications Using the Web Service and the .NET Framework](../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md).</span></span>  
  
10. <span data-ttu-id="963dc-127">Expanda el nodo del proyecto en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="963dc-127">In Solution Explorer, expand the project node.</span></span> <span data-ttu-id="963dc-128">Verá que se ha agregado un archivo de código con el nombre predeterminado Program.cs (Module1.vb para [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) al proyecto.</span><span class="sxs-lookup"><span data-stu-id="963dc-128">You will see a code file with the default name of Program.cs (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) has been added to your project.</span></span>  
  
11. <span data-ttu-id="963dc-129">Abra el archivo Program.cs (Module1.vb para [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) y reemplace el código por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="963dc-129">Open the Program.cs (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) file and replace the code with the following:</span></span>  
  
     <span data-ttu-id="963dc-130">El siguiente código proporciona los códigos auxiliares del método que se utilizarán para implementar funcionalidad para cargar, actualizar y guardar.</span><span class="sxs-lookup"><span data-stu-id="963dc-130">The following code provides the method stubs we will use to implement the Load, Update and Save functionality.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.IO;  
    using System.Text;  
    using System.Xml;  
    using System.Xml.Serialization;  
    using ReportService2010;  
  
    namespace SampleRDLSchema  
    {  
        class ReportUpdater  
        {  
            ReportingService2010 _reportService;  
  
            static void Main(string[] args)  
            {  
                ReportUpdater reportUpdater = new ReportUpdater();  
                reportUpdater.UpdateReport();  
            }  
  
            private void UpdateReport()  
            {  
                try  
                {  
                    // Set up the Report Service connection  
                    _reportService = new ReportingService2010();  
                    _reportService.Credentials =  
                        System.Net.CredentialCache.DefaultCredentials;  
                    _reportService.Url =  
                       "http://<Server Name>/reportserver/" +  
                                       "reportservice2010.asmx";  
  
                    // Call the methods to update a report definition  
                    LoadReportDefinition();  
                    UpdateReportDefinition();  
                    PublishReportDefinition();  
                }  
                catch (Exception ex)  
                {  
                    System.Console.WriteLine(ex.Message);  
                }  
            }  
  
            private void LoadReportDefinition()  
            {  
                //Lesson 3: Load a report definition from the report   
                //          catalog  
            }  
  
            private void UpdateReportDefinition()  
            {  
                //Lesson 4: Update the report definition using the    
                //          classes generated from the RDL Schema  
            }  
  
            private void PublishReportDefinition()  
            {  
                //Lesson 5: Publish the updated report definition back   
                //          to the report catalog  
            }  
        }  
    }  
    ```  
  
    ```vb  
    Imports System  
    Imports System.Collections.Generic  
    Imports System.IO  
    Imports System.Text  
    Imports System.Xml  
    Imports System.Xml.Serialization  
    Imports ReportService2010  
  
    Namespace SampleRDLSchema  
  
        Module ReportUpdater  
  
            Private m_reportService As ReportingService2010  
  
            Public Sub Main(ByVal args As String())  
  
                Try  
                    'Set up the Report Service connection  
                    m_reportService = New ReportingService2010  
                    m_reportService.Credentials = _  
                        System.Net.CredentialCache.DefaultCredentials  
                    m_reportService.Url = _  
                        "http:// <Server Name>/reportserver/" & _  
                               "reportservice2010.asmx"  
  
                    'Call the methods to update a report definition  
                    LoadReportDefinition()  
                    UpdateReportDefinition()  
                    PublishReportDefinition()  
                Catch ex As Exception  
                    System.Console.WriteLine(ex.Message)  
                End Try  
  
            End Sub  
  
            Private Sub LoadReportDefinition()  
                'Lesson 3: Load a report definition from the report   
                '          catalog  
            End Sub  
  
            Private Sub UpdateReportDefinition()  
                'Lesson 4: Update the report definition using the   
                '          classes generated from the RDL Schema  
            End Sub  
  
            Private Sub PublishReportDefinition()  
                'Lesson 5: Publish the updated report definition back   
                '          to the report catalog  
            End Sub  
  
        End Module  
  
    End Namespace   
    ```  
  
## <a name="next-lesson"></a><span data-ttu-id="963dc-131">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="963dc-131">Next Lesson</span></span>  
 <span data-ttu-id="963dc-132">En la siguiente lección utilizará la herramienta de definición de esquemas XML (Xsd.exe) para generar clases a partir del esquema RDL e incluirlas en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="963dc-132">In the next lesson, you will use the XML Schema Definition Tool (Xsd.exe) to generate classes from the RDL schema and include them in your project.</span></span> <span data-ttu-id="963dc-133">Vea [Lección 2: generar clases a partir del esquema RDL con la herramienta XSD](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md).</span><span class="sxs-lookup"><span data-stu-id="963dc-133">See [Lesson 2: Generate Classes from the RDL Schema using the xsd Tool](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="963dc-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="963dc-134">See Also</span></span>  
 <span data-ttu-id="963dc-135">[Actualizar informes con clases generadas a partir del esquema RDL &#40;tutorial de SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="963dc-135">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="963dc-136">Lenguaje RDL (Report Definition Language) &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="963dc-136">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
