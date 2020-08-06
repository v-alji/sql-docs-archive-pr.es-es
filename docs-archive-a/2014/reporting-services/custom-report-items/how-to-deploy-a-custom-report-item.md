---
title: 'Procedimientos: Implementación de un elemento de informe personalizado | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, deploying
ms.assetid: 80e97b0d-e355-4240-aebd-08cbc84089ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 66519610526478caadeb41b48c9823414e88d5d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750530"
---
# <a name="how-to-deploy-a-custom-report-item"></a><span data-ttu-id="245c4-102">Procedimientos: Implementación de un elemento de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="245c4-102">How to: Deploy a Custom Report Item</span></span>
  <span data-ttu-id="245c4-103">Para implementar un elemento de informe personalizado en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], debe modificar los archivos de configuración del servidor de informes y copiar los ensamblados de componentes en tiempo de diseño y en tiempo de ejecución a las carpetas de aplicación correspondientes para el Diseñador de informes y el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="245c4-103">To deploy a custom report item in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must modify the report server configuration files and copy the design-time and run-time component assemblies into the appropriate application folders for both Report Designer and the report server.</span></span>  
  
### <a name="to-deploy-a-custom-report-item"></a><span data-ttu-id="245c4-104">Para implementar un elemento de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="245c4-104">To deploy a custom report item</span></span>  
  
1.  <span data-ttu-id="245c4-105">Modifique el archivo Rsreportdesigner.config para configurar los componentes de tiempo de ejecución y de tiempo de diseño de elementos de informe personalizados que se utilizarán en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="245c4-105">Edit the Rsreportdesigner.config file to configure the custom report item run-time and design-time components for use in the designer.</span></span> <span data-ttu-id="245c4-106">Observe que la entrada `ReportItemName` debe coincidir con el atributo `CustomReportItemAttribute` utilizado en la clase `CustomReportItemDesigner`.</span><span class="sxs-lookup"><span data-stu-id="245c4-106">Note that the `ReportItemName` entry must match the `CustomReportItemAttribute` attribute used in your `CustomReportItemDesigner` class.</span></span> <span data-ttu-id="245c4-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="245c4-107">For example:</span></span>  
  
    ```  
    <ReportItems>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsCRI,PolygonsCRI"/>  
    </ReportItems>  
    <ReportItemDesigner>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsDesigner, PolygonsDesigner" />  
    </ReportItemDesigner>  
    <ReportItemConverter>  
       <Converter Source="Chart" Target="Polygons" Type="PolygonsCRI.PolygonsConverter, PolygonsDesigner" />  
    </ReportItemConverter>  
    ```  
  
2.  <span data-ttu-id="245c4-108">Modifique el archivo Rsreportserver.config para registrar el componente de tiempo de ejecución del elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="245c4-108">Edit the Rsreportserver.config file to register the custom report item run-time component.</span></span> <span data-ttu-id="245c4-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="245c4-109">For example:</span></span>  
  
    ```  
    <ReportItems>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsCRI,PolygonsCRI"/>  
    </ReportItems>  
    ```  
  
3.  <span data-ttu-id="245c4-110">Modifique el archivo Rsssrvpolicy.config para agregar un `CodeGroup` que conceda los permisos apropiados al elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="245c4-110">Edit the Rsssrvpolicy.config file to add a `CodeGroup` that grants the proper permissions to the custom report item.</span></span> <span data-ttu-id="245c4-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="245c4-111">For example:</span></span>  
  
    ```  
    <CodeGroup   
       class="UnionCodeGroup"   
       version="1"   
       PermissionSetName="FullTrust"  
       Description="This code group grants MyCustomReportItem.dll FullTrust permission. ">  
       <IMembershipCondition   
          class="UrlMembershipCondition"  
          version="1"  
       Url="C:\Program Files\Microsoft SQL Server\ MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin\MyCustomReportItem.dll" />  
    </CodeGroup>  
    ```  
  
4.  <span data-ttu-id="245c4-112">Copie el DLL de componente de tiempo de ejecución del elemento de informe en los directorios \Archivos de programa\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies y %Archivos de programa%\Microsoft SQL Server\MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="245c4-112">Copy the custom report item run-time component DLL to the %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies and \Program Files\Microsoft SQL Server\MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin directories.</span></span>  
  
5.  <span data-ttu-id="245c4-113">Copie el DLL de componente de tiempo de diseño de elemento de informe en el directorio %Archivos de programa%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="245c4-113">Copy the custom report item design-time component DLL to the %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="245c4-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="245c4-114">See Also</span></span>  
 <span data-ttu-id="245c4-115">[Archivos de configuración de Reporting Services](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="245c4-115">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="245c4-116">Bibliotecas de clases de elemento de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="245c4-116">Custom Report Item Class Libraries</span></span>](custom-report-item-class-libraries.md)  
  
  
