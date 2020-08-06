---
title: Buscar elementos de informe y establecer una carpeta predeterminada (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5cf38068-65d1-4fe8-81f3-a404d8fbc663
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6605a23732799ec07b3dbe8481e88c91b18ebe5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663915"
---
# <a name="browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs"></a><span data-ttu-id="5854f-102">Buscar elementos de informe y establecer una carpeta predeterminada (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="5854f-102">Browse for Report Parts and Set a Default Folder (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5854f-103">La manera más fácil de crear un informe es agregarle elementos, como tablas y gráficos, de la galería de elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="5854f-103">The easiest way to create a report is to add existing report parts, such as tables and charts, to your report from the Report Part Gallery.</span></span> <span data-ttu-id="5854f-104">Al agregar un elemento de informe al informe, también agrega todo lo que debe tener para que funcione.</span><span class="sxs-lookup"><span data-stu-id="5854f-104">When you add a report part to your report, you are also adding everything it must have to work.</span></span> <span data-ttu-id="5854f-105">Por ejemplo, cualquier elemento de informe que muestre los datos depende de un conjunto de datos, es decir, una consulta y una conexión a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5854f-105">For example, any report part that displays data depends on a dataset, that is, a query and a connection to a data source.</span></span> <span data-ttu-id="5854f-106">Después de agregar el elemento de informe a un informe, puede modificarlo como convenga.</span><span class="sxs-lookup"><span data-stu-id="5854f-106">After you add the report part to your report, you can modify it as much as you need.</span></span>  
  
 <span data-ttu-id="5854f-107">Puede establecer una carpeta predeterminada para publicar elementos de informe en el servidor de informes o el sitio de SharePoint integrado con un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5854f-107">You can set a default folder to publish report parts to the report server or SharePoint site integrated with a report server.</span></span>  
  
 <span data-ttu-id="5854f-108">Para más información, vea [Elementos de informe &#40;Generador de informes y SSRS&#41;](../report-parts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5854f-108">For more information, see [Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-browse-for-report-parts"></a><span data-ttu-id="5854f-109">Para buscar elementos de informe</span><span class="sxs-lookup"><span data-stu-id="5854f-109">To browse for report parts</span></span>  
  
1.  <span data-ttu-id="5854f-110">En el menú **Insertar** , haga clic en **Elementos de informe**.</span><span class="sxs-lookup"><span data-stu-id="5854f-110">On the **Insert** menu, click **Report Parts**.</span></span>  
  
     <span data-ttu-id="5854f-111">Si no está conectado, haga clic en **Conectar con un servidor de informes**y escriba el nombre.</span><span class="sxs-lookup"><span data-stu-id="5854f-111">If you are not already connected, click **Connect to a report server**, and enter the name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5854f-112">Debe estar conectado a un servidor de informes para buscar elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="5854f-112">You must be connected to a report server to browse for report parts.</span></span>  
  
2.  <span data-ttu-id="5854f-113">Puede restringir la búsqueda especificando detalles sobre el elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="5854f-113">You can narrow your search by specifying details about the report part.</span></span> <span data-ttu-id="5854f-114">Escriba todo o parte del nombre y la descripción en el cuadro **Buscar** , o haga clic **Agregar criterios** y agregue los valores para alguno de los campos o para todos:</span><span class="sxs-lookup"><span data-stu-id="5854f-114">Type all or part of the name and description in the **Search** box, or click **Add Criteria** and add values for any or all of these fields:</span></span>  
  
    -   <span data-ttu-id="5854f-115">Creado por</span><span class="sxs-lookup"><span data-stu-id="5854f-115">Created by</span></span>  
  
    -   <span data-ttu-id="5854f-116">Fecha de creación</span><span class="sxs-lookup"><span data-stu-id="5854f-116">Date created</span></span>  
  
    -   <span data-ttu-id="5854f-117">Fecha de última modificación</span><span class="sxs-lookup"><span data-stu-id="5854f-117">Date last modified</span></span>  
  
    -   <span data-ttu-id="5854f-118">Última modificación por</span><span class="sxs-lookup"><span data-stu-id="5854f-118">Last modified by</span></span>  
  
    -   <span data-ttu-id="5854f-119">Carpeta del servidor</span><span class="sxs-lookup"><span data-stu-id="5854f-119">Server folder</span></span>  
  
    -   <span data-ttu-id="5854f-120">Tipo</span><span class="sxs-lookup"><span data-stu-id="5854f-120">Type</span></span>  
  
     <span data-ttu-id="5854f-121">Por ejemplo, para encontrar una imagen, haga clic en **Agregar criterios**y, a continuación, haga clic en **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="5854f-121">For example, to find an image, click **Add Criteria**, and then click **Type**.</span></span> <span data-ttu-id="5854f-122">En la lista desplegable, active la casilla **Imagen** , presione ENTRAR y, a continuación, haga clic en la lupa de Buscar.</span><span class="sxs-lookup"><span data-stu-id="5854f-122">In the dropdown box, select the **Image** check box, press ENTER, and then click the Search magnifying glass.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5854f-123">Para los valores de **Creado por** y **Última modificación por** , busque el nombre de usuario de la persona como se representa en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5854f-123">For the **Created by** and **Last modified by** values, search for the person's user name as it is represented on the report server.</span></span>  
  
### <a name="to-set-a-default-folder-for-report-parts"></a><span data-ttu-id="5854f-124">Para establecer una carpeta predeterminada para elementos de informe</span><span class="sxs-lookup"><span data-stu-id="5854f-124">To set a default folder for report parts</span></span>  
  
1.  <span data-ttu-id="5854f-125">Haga clic en **Generador de informes**y, a continuación, en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="5854f-125">Click **Report Builder**, and then click **Options**.</span></span>  
  
2.  <span data-ttu-id="5854f-126">En el cuadro de diálogo **Opciones** , en la pestaña **Configuración** , escriba un nombre de carpeta en el cuadro de texto **Publicar elementos de informe en esta carpeta de forma predeterminada** .</span><span class="sxs-lookup"><span data-stu-id="5854f-126">In the **Options** dialog box, on the **Settings** tab, type a folder name in the **Publish report parts to this folder by default** textbox.</span></span>  
  
 <span data-ttu-id="5854f-127">El Generador de informes creará esta carpeta si se dispone de permisos para crear carpetas en el servidor de informes y la carpeta no existe todavía.</span><span class="sxs-lookup"><span data-stu-id="5854f-127">Report Builder will create this folder if you have permissions to create folders on the report server and the folder does not exist yet.</span></span>  
  
 <span data-ttu-id="5854f-128">No necesita reiniciar el Generador de informes para que esta configuración surta efecto.</span><span class="sxs-lookup"><span data-stu-id="5854f-128">You do not need to restart Report Builder for this setting to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5854f-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5854f-129">See Also</span></span>  
 <span data-ttu-id="5854f-130">[Buscar actualizaciones o desactivar las actualizaciones de &#40;Generador de informes y SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5854f-130">[Check for Updates or Turn Updates Off &#40;Report Builder and SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5854f-131">[Elementos de informe &#40;Generador de informes y SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5854f-131">[Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5854f-132">[Elementos de informe y conjuntos de datos en el Generador de informes](../report-data/report-parts-and-datasets-in-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="5854f-132">[Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md) </span></span>  
 <span data-ttu-id="5854f-133">[Solucionar problemas de elementos de informe &#40;Generador de informes y SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5854f-133">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5854f-134">Publicar y volver a publicar elementos de informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5854f-134">Publish and Republish Report Parts &#40;Report Builder and SSRS&#41;</span></span>](publish-and-republish-report-parts-report-builder-and-ssrs.md)  
  
  
