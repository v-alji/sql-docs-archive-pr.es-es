---
title: Crear un componente de tiempo de ejecución de elemento de informe personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, creating
ms.assetid: b3e15a4a-98f8-4dbb-b847-bbcb20327051
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 50c5c0211bc5cd1359af9d1493782bd9d96c2b3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662677"
---
# <a name="creating-a-custom-report-item-run-time-component"></a><span data-ttu-id="1c5a8-102">Crear un componente de tiempo de ejecución de elemento de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="1c5a8-102">Creating a Custom Report Item Run-Time Component</span></span>
  <span data-ttu-id="1c5a8-103">El componente de tiempo de ejecución del elemento de informe personalizado se implementa como un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] componente de mediante cualquier lenguaje conforme a CLS y el procesador de informes lo llama en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c5a8-103">The custom report item run-time component is implemented as a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] component using any CLS-compliant language, and is called by the report processor at run time.</span></span> <span data-ttu-id="1c5a8-104">Las propiedades para el componente de tiempo de ejecución en el entorno de diseño se definen modificando el componente de tiempo de diseño correspondiente del elemento de informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="1c5a8-104">You define the properties for the run-time component in the design environment by modifying the custom report item's corresponding design-time component.</span></span>  

<!--
Replacing the following multiValue.....

ms.technology: 
  - "docset-sql-devref"
  - "reporting-services-native"

.....with the following single value.....

ms.technology: reporting-services
.

(GeneMi = MightyPen  ,  2019-04-20  ,  DevO= 1515083)
-->

 <span data-ttu-id="1c5a8-105">Para obtener un ejemplo de un elemento de informe personalizado totalmente implementado, vea [Ejemplos del producto SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="1c5a8-105">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="definition-and-instance-objects"></a><span data-ttu-id="1c5a8-106">Objetos de definición e instancia</span><span class="sxs-lookup"><span data-stu-id="1c5a8-106">Definition and Instance Objects</span></span>  
 <span data-ttu-id="1c5a8-107">Antes de implementar un elemento de informe personalizado, es importante entender la diferencia entre *objetos de definición* y *objetos de instancia*.</span><span class="sxs-lookup"><span data-stu-id="1c5a8-107">Before implementing a custom report item it is important to understand the difference between *definition objects* and *instance objects*.</span></span> <span data-ttu-id="1c5a8-108">Los objetos de definición proporcionan la representación RDL del elemento de informe personalizado mientras que objetos de instancia son las versiones evaluadas de los objetos de definición.</span><span class="sxs-lookup"><span data-stu-id="1c5a8-108">Definition objects provide the RDL representation of the custom report item whereas instance objects are the evaluated versions of the definition objects.</span></span> <span data-ttu-id="1c5a8-109">Hay solo un objeto de definición para cada elemento en el informe.</span><span class="sxs-lookup"><span data-stu-id="1c5a8-109">There is only one definition object for each item on the report.</span></span> <span data-ttu-id="1c5a8-110">Al tener acceso a las propiedades en un objeto de definición que contiene expresiones, obtendrá una cadena de expresión no evaluada.</span><span class="sxs-lookup"><span data-stu-id="1c5a8-110">When accessing properties on a definition object that contain expressions, you will get the unevaluated expression string.</span></span> <span data-ttu-id="1c5a8-111">Los objetos de instancia contienen las versiones evaluadas de los objetos de definición y pueden tener una relación uno a varios con el objeto de definición de un elemento.</span><span class="sxs-lookup"><span data-stu-id="1c5a8-111">Instance objects contain the evaluated versions of the definition objects and can have a one-to-many relationship with an item's definition object.</span></span> <span data-ttu-id="1c5a8-112">Por ejemplo, si un informe tiene una región de datos <xref:Microsoft.ReportingServices.OnDemandReportRendering.Tablix> que contiene un <xref:Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem> en una fila de detalle, solo habrá un objeto de definición, pero habrá un objeto de instancia para cada fila en la región de datos.</span><span class="sxs-lookup"><span data-stu-id="1c5a8-112">For example, if a report has a <xref:Microsoft.ReportingServices.OnDemandReportRendering.Tablix> data region that contains a <xref:Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem> in a detail row, there will be only one definition object but there will be an instance object for each row in the data region.</span></span>  
  
## <a name="implementing-the-icustomreportitem-interface"></a><span data-ttu-id="1c5a8-113">Implementar la interfaz ICustomReportItem</span><span class="sxs-lookup"><span data-stu-id="1c5a8-113">Implementing the ICustomReportItem Interface</span></span>  
 <span data-ttu-id="1c5a8-114">Para crear un componente de tiempo de ejecución `CustomReportItem`, necesitará implementar la interfaz <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem> que se define en Microsoft.ReportingServices.ProcessingCore.dll:</span><span class="sxs-lookup"><span data-stu-id="1c5a8-114">To create a `CustomReportItem` run-time component you will need to implement the <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem> interface that is defined in the Microsoft.ReportingServices.ProcessingCore.dll:</span></span>  
  
```csharp  
namespace Microsoft.ReportingServices.OnDemandReportRendering  
{  
    public interface ICustomReportItem  
    {  
        void GenerateReportItemDefinition(CustomReportItem customReportItem);  
void EvaluateReportItemInstance(CustomReportItem customReportItem);  
    }  
}  
```  
  
 <span data-ttu-id="1c5a8-115">Después de haber implementado la interfaz <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem>, se generarán dos códigos auxiliares de método: <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> y <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="1c5a8-115">After you have implemented the <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem> interface, two method stubs will be generated for you: <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> and <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A>.</span></span> <span data-ttu-id="1c5a8-116">El método <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> se llama primero y se utiliza para establecer las propiedades de definición y crear el objeto <xref:Microsoft.ReportingServices.OnDemandReportRendering.Image> que contendrá las propiedades de instancia y definición que se utilizan para representar el elemento.</span><span class="sxs-lookup"><span data-stu-id="1c5a8-116">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> method is called first and is used for setting definition properties and creating the <xref:Microsoft.ReportingServices.OnDemandReportRendering.Image> object that will contain both the definition and instance properties that are used for rendering the item.</span></span> <span data-ttu-id="1c5a8-117">Se llama al método <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A> una vez evaluados los objetos de definición, y este método proporciona los objetos de instancia que se utilizarán para representar el elemento.</span><span class="sxs-lookup"><span data-stu-id="1c5a8-117">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A> method is called after the definition objects have been evaluated, and it provides the instance objects that will be used for rendering the item.</span></span>  
  
 <span data-ttu-id="1c5a8-118">La siguiente es una implementación de ejemplo de un elemento de informe personalizado que representa el nombre del control como una imagen.</span><span class="sxs-lookup"><span data-stu-id="1c5a8-118">The following is an example implementation of a custom report item that renders the name of the control as an image.</span></span>  
  
```csharp  
namespace Microsoft.Samples.ReportingServices  
{  
    using System;  
    using System.Collections.Generic;  
    using System.Collections.Specialized;  
    using System.Drawing.Imaging;  
    using System.IO;  
    using System.Text;  
    using Microsoft.ReportingServices.OnDemandReportRendering;  
  
    public class PolygonsCustomReportItem : ICustomReportItem  
    {  
        #region ICustomReportItem Members  
  
        public void GenerateReportItemDefinition(CustomReportItem cri)  
        {  
            // Create the Image object that will be   
            // used to render the custom report item  
            cri.CreateCriImageDefinition();  
            Image polygonImage = (Image)cri.GeneratedReportItem;  
        }  
  
        public void EvaluateReportItemInstance(CustomReportItem cri)  
        {  
            // Get the Image definition  
            Image polygonImage = (Image)cri.GeneratedReportItem;  
  
            // Create the image for the custom report item  
            polygonImage.ImageInstance.ImageData = DrawImage(cri);  
        }  
  
        #endregion  
  
        /// <summary>  
        /// Creates an image of the CustomReportItem's name  
        /// </summary>  
        private byte[] DrawImage(CustomReportItem customReportItem)  
        {  
            int width = 1;          // pixels  
            int height = 1;         // pixels  
            int resolution = 75;    // dpi  
  
            System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap(width, height);  
            bitmap.SetResolution(resolution, resolution);  
  
            System.Drawing.Graphics graphics = System.Drawing.Graphics.FromImage(bitmap);  
            graphics.PageUnit = System.Drawing.GraphicsUnit.Pixel;  
  
            // Get the Font for the Text  
            System.Drawing.Font font = new System.Drawing.Font(System.Drawing.FontFamily.GenericMonospace,  
                12, System.Drawing.FontStyle.Regular);  
  
            // Get the Brush for drawing the Text  
            System.Drawing.Brush brush = new System.Drawing.SolidBrush(System.Drawing.Color.LightGreen);  
  
            // Get the measurements for the image  
            System.Drawing.SizeF maxStringSize = graphics.MeasureString(customReportItem.Name, font);  
            width = (int)(maxStringSize.Width + 2 * font.GetHeight(resolution));  
            height = (int)(maxStringSize.Height + 2 * font.GetHeight(resolution));  
  
            bitmap.Dispose();  
            bitmap = new System.Drawing.Bitmap(width, height);  
            bitmap.SetResolution(resolution, resolution);  
  
            graphics.Dispose();  
            graphics = System.Drawing.Graphics.FromImage(bitmap);  
            graphics.PageUnit = System.Drawing.GraphicsUnit.Pixel;  
  
            // Draw the text  
            graphics.DrawString(customReportItem.Name, font, brush, font.GetHeight(resolution),   
                font.GetHeight(resolution));  
  
            // Create the byte array of the image data  
            MemoryStream memoryStream = new MemoryStream();  
            bitmap.Save(memoryStream, ImageFormat.Bmp);  
            memoryStream.Position = 0;  
            byte[] imageData = new byte[memoryStream.Length];  
            memoryStream.Read(imageData, 0, imageData.Length);  
  
            return imageData;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c5a8-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c5a8-119">See Also</span></span>  
 <span data-ttu-id="1c5a8-120">[Arquitectura de elementos de informe personalizados](custom-report-item-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="1c5a8-120">[Custom Report Item Architecture](custom-report-item-architecture.md) </span></span>  
 <span data-ttu-id="1c5a8-121">[Crear un componente de tiempo de diseño de elemento de informe personalizado](creating-a-custom-report-item-design-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="1c5a8-121">[Creating a Custom Report Item Design-Time Component](creating-a-custom-report-item-design-time-component.md) </span></span>  
 <span data-ttu-id="1c5a8-122">[Bibliotecas de clases de elementos de informe personalizadas](custom-report-item-class-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="1c5a8-122">[Custom Report Item Class Libraries](custom-report-item-class-libraries.md) </span></span>  
 [<span data-ttu-id="1c5a8-123">Cómo: Implementar un elemento de informe personalizado</span><span class="sxs-lookup"><span data-stu-id="1c5a8-123">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
  
  
