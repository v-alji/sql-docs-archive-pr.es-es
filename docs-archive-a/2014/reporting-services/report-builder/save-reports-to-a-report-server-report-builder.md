---
title: Guardar informes en un servidor de informes (Generador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 48dfef01-ed8c-4f23-90c3-de67c90a97dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d80e35c447593e89d422e72ea31ec6be34c3619f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749140"
---
# <a name="save-reports-to-a-report-server-report-builder"></a><span data-ttu-id="4b58e-102">Guardar informes en un servidor de informes (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="4b58e-102">Save Reports to a Report Server (Report Builder)</span></span>
  <span data-ttu-id="4b58e-103">En el Generador de informes, puede guardar una definición de informe en un servidor de informes (a lo que también se hace referencia como publicar un informe).</span><span class="sxs-lookup"><span data-stu-id="4b58e-103">In Report Builder, you can save a report definition to a report server (also known as publishing a report).</span></span> <span data-ttu-id="4b58e-104">Cuando el informe está guardado en un servidor de informes, otros usuarios pueden verlo.</span><span class="sxs-lookup"><span data-stu-id="4b58e-104">When the report is saved to a report server, other users can view the report.</span></span> <span data-ttu-id="4b58e-105">Cada vez que ejecute el informe publicado, recuperará los datos más actuales.</span><span class="sxs-lookup"><span data-stu-id="4b58e-105">Each time you run the published report, you will retrieve the most current data.</span></span> <span data-ttu-id="4b58e-106">Para guardar una copia estática de un informe representado, exporte el informe a un formato de archivo diferente y guárdelo o utilice la característica de historial de informes para guardar las versiones de los informes representados.</span><span class="sxs-lookup"><span data-stu-id="4b58e-106">To save a static copy of a rendered report, export the report to a different file format and save it or use the report history feature to save versions of rendered reports.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b58e-107">La ubicación de la definición de informe guardado no afecta al hecho de que el informe se procese en el servidor o se procese localmente cuando obtiene una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="4b58e-107">The location of the saved report definition does not affect whether the report is processed on the server or processed locally when you preview the report.</span></span>  
  
### <a name="to-save-a-report-to-a-report-server"></a><span data-ttu-id="4b58e-108">Guardar un informe en un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="4b58e-108">To save a report to a report server</span></span>  
  
1.  <span data-ttu-id="4b58e-109">Desde el botón Generador de informes, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4b58e-109">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="4b58e-110">Se abre el cuadro de diálogo **Guardar como** _\<Report Item\>_ .</span><span class="sxs-lookup"><span data-stu-id="4b58e-110">The **Save As**_\<Report Item\>_ dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4b58e-111">Si vuelve a guardar un informe, automáticamente se guarda en su ubicación anterior.</span><span class="sxs-lookup"><span data-stu-id="4b58e-111">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="4b58e-112">Utilice la opción Guardar como para cambiar la ubicación.</span><span class="sxs-lookup"><span data-stu-id="4b58e-112">Use the Save As option to change location.</span></span>  
  
2.  <span data-ttu-id="4b58e-113">Si lo desea, puede hacer clic en **Sitios y servidores recientes** para mostrar una lista de servidores de informes y sitios de SharePoint utilizados recientemente.</span><span class="sxs-lookup"><span data-stu-id="4b58e-113">Optionally, click **Recent Sites and Servers** to show a list of recently used report servers and SharePoint sites.</span></span>  
  
3.  <span data-ttu-id="4b58e-114">Busque la ubicación del servidor de informes en la que desea guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="4b58e-114">Browse to the report server location where you want to save the report.</span></span>  
  
4.  <span data-ttu-id="4b58e-115">En **Nombre**, escriba el nombre del informe.</span><span class="sxs-lookup"><span data-stu-id="4b58e-115">In **Name**, type the name of the report.</span></span>  
  
5.  <span data-ttu-id="4b58e-116">En **Elementos de tipo**, seleccione el tipo de elemento de informe que está guardando.</span><span class="sxs-lookup"><span data-stu-id="4b58e-116">In **Items of type**, select the type of report item you are saving.</span></span> <span data-ttu-id="4b58e-117">El tipo para los informes es Informes (\*.rdl).</span><span class="sxs-lookup"><span data-stu-id="4b58e-117">The type for reports is Reports(\*.rdl).</span></span>  
  
### <a name="to-save-a-report-as-a-different-name"></a><span data-ttu-id="4b58e-118">Para guardar un informe con un nombre diferente</span><span class="sxs-lookup"><span data-stu-id="4b58e-118">To save a report as a different name</span></span>  
  
1.  <span data-ttu-id="4b58e-119">En el botón Generador de informes , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="4b58e-119">From the Report Builder button, click **Save As**.</span></span> <span data-ttu-id="4b58e-120">Se abre el cuadro de diálogo **Guardar como** _\<Report Item\>_ .</span><span class="sxs-lookup"><span data-stu-id="4b58e-120">The **Save As**_\<Report Item\>_ dialog box opens.</span></span>  
  
2.  <span data-ttu-id="4b58e-121">Vaya a la ubicación del servidor de informes o al recurso compartido de archivos donde desea guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="4b58e-121">Browse to the report server location or to the file share where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="4b58e-122">En **Nombre**, escriba el nombre del informe.</span><span class="sxs-lookup"><span data-stu-id="4b58e-122">In **Name**, type the name of the report.</span></span>  
  
4.  <span data-ttu-id="4b58e-123">En **Elementos de tipo**, seleccione el tipo de elemento de informe que está guardando.</span><span class="sxs-lookup"><span data-stu-id="4b58e-123">In **Items of type**, select the type of report item you are saving.</span></span> <span data-ttu-id="4b58e-124">El tipo para los informes es Informes (\*.rdl).</span><span class="sxs-lookup"><span data-stu-id="4b58e-124">The type for reports is Reports(\*.rdl).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b58e-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b58e-125">See Also</span></span>  
 <span data-ttu-id="4b58e-126">[Buscar, ver y administrar informes &#40;Generador de informes y SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4b58e-126">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4b58e-127">[Exportar informes &#40;Generador de informes y SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="4b58e-127">[Exporting Reports &#40;Report Builder and SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="4b58e-128">[Guardar informes &#40;Generador de informes&#41;](saving-reports-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="4b58e-128">[Saving Reports &#40;Report Builder&#41;](saving-reports-report-builder.md) </span></span>  
 [<span data-ttu-id="4b58e-129">Exportar un informe como otro tipo de archivo &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4b58e-129">Export a Report as Another File Type &#40;Report Builder and SSRS&#41;</span></span>](../export-a-report-as-another-file-type-report-builder-and-ssrs.md)  
  
  
