---
title: Publicar y volver a publicar elementos de informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 92dce484-f39b-403c-9caf-d8772bc3aca3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 95fd5e3f7519c6a0d4a6f08cb9bcbf2507d32aaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671377"
---
# <a name="publish-and-republish-report-parts-report-builder-and-ssrs"></a><span data-ttu-id="8757a-102">Publicar y volver a publicar elementos de informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="8757a-102">Publish and Republish Report Parts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8757a-103">Puede publicar un elemento de informe con la configuración predeterminada en una ubicación predeterminada, o editar los metadatos del elemento de informe , por ejemplo el nombre y la descripción, y guardarlo en otra ubicación de un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="8757a-103">You can publish a report part with default settings in a default location, or you can edit report part metadata such as name and description, and save it somewhere else on a report server.</span></span> <span data-ttu-id="8757a-104">También puede guardarlo en un sitio de SharePoint que esté integrado con un servidor de informes si tiene los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="8757a-104">You can also save it to a SharePoint site that is integrated with a report server if you have the correct permissions.</span></span>  
  
 <span data-ttu-id="8757a-105">Puede publicar solo el elemento de informe, con el conjunto de datos del que depende incrustado en él, o publicar el conjunto de datos por separado.</span><span class="sxs-lookup"><span data-stu-id="8757a-105">You can publish just the report part, with the dataset that it depends on embedded in it, or you can publish the dataset separately.</span></span> <span data-ttu-id="8757a-106">Si publica el conjunto de datos por separado, se convierte en un conjunto de datos compartido y el elemento de informe se vincula con él.</span><span class="sxs-lookup"><span data-stu-id="8757a-106">If you publish the dataset separately, it becomes a shared dataset, and the report part links to it.</span></span> <span data-ttu-id="8757a-107">Para obtener más información, vea [Elementos de informe y conjuntos de datos en el Generador de informes](../report-data/report-parts-and-datasets-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="8757a-107">For more information, see [Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md).</span></span>  
  
 <span data-ttu-id="8757a-108">Puede volver a publicar un elemento de informe existente.</span><span class="sxs-lookup"><span data-stu-id="8757a-108">You can republish an existing report part.</span></span> <span data-ttu-id="8757a-109">Si tiene los permisos necesarios, puede volver a guardar la instancia original del elemento de informe en el servidor, aunque no lo haya creado.</span><span class="sxs-lookup"><span data-stu-id="8757a-109">If you have permissions, you can save over the original instance of the report part on the server, even if you didn't create it.</span></span> <span data-ttu-id="8757a-110">También puede publicarlo como un nuevo elemento de informe y guardarlo en la misma ubicación o en otra.</span><span class="sxs-lookup"><span data-stu-id="8757a-110">You can also publish it as a new report part and save it either in the same or a different location.</span></span>  
  
### <a name="to-publish-a-report-part"></a><span data-ttu-id="8757a-111">Para publicar un elemento de informe</span><span class="sxs-lookup"><span data-stu-id="8757a-111">To publish a report part</span></span>  
  
1.  <span data-ttu-id="8757a-112">En el menú del Generador de informes, haga clic en **Publicar elementos de informe**.</span><span class="sxs-lookup"><span data-stu-id="8757a-112">On the Report Builder menu, click **Publish Report Parts**.</span></span>  
  
     <span data-ttu-id="8757a-113">Si no está conectado a un servidor de informes, se le pedirá que lo haga.</span><span class="sxs-lookup"><span data-stu-id="8757a-113">If you are not connected to a report server, you will be prompted to connect.</span></span> <span data-ttu-id="8757a-114">Si no puede conectarse a un servidor de informes, no puede publicar elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="8757a-114">If you cannot connect to a report server, you cannot publish report parts.</span></span>  
  
2.  <span data-ttu-id="8757a-115">Para guardar elementos de informe con la configuración predeterminada en la ubicación predeterminada, haga clic en **Publicar todos los elementos de informe con configuración predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="8757a-115">To save your report parts with default settings to the default location, click **Publish all report parts with default settings**.</span></span>  
  
     <span data-ttu-id="8757a-116">Si no desea hacerlo, haga clic en **Revisar y modificar los elementos de informe antes de publicarlos**.</span><span class="sxs-lookup"><span data-stu-id="8757a-116">Otherwise, click **Review and modify report parts before publishing**.</span></span>  
  
3.  <span data-ttu-id="8757a-117">Edite el nombre y la descripción del elemento de informe. Haga doble clic en el nombre para editarlo y haga clic en el campo **Descripción** para agregar una descripción.</span><span class="sxs-lookup"><span data-stu-id="8757a-117">Edit the report part name and description: Double-click the name to edit it and click in the **Description** field to add a description.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8757a-118">Es aconsejable dar un nombre y una descripción al elemento de informe, porque ayuda a los usuarios a identificarlo cuando lo buscan.</span><span class="sxs-lookup"><span data-stu-id="8757a-118">It is a good idea to give the report part name and description, to help people identify it when searching.</span></span> <span data-ttu-id="8757a-119">La longitud máxima del nombre de un elemento de informe es de 260 caracteres para la ruta de acceso completa, incluidos los nombres de las carpetas del servidor, seguidos por el nombre del elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="8757a-119">The maximum length for the name of a report part is 260 characters for the entire path, including the names of the folders on the server, followed by the actual name of the report part.</span></span>  
  
4.  <span data-ttu-id="8757a-120">Para guardar un elemento de informe en una carpeta que no sea la predeterminada, haga clic en el botón **Examinar** .</span><span class="sxs-lookup"><span data-stu-id="8757a-120">To save your report part to a folder other than the default, click the **Browse** button.</span></span>  
  
5.  <span data-ttu-id="8757a-121">Cuando haya configurado las opciones para todos los elementos de informe del informe, haga clic en **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="8757a-121">When you have set the options for all the report parts in the report, click **Publish**.</span></span>  
  
     <span data-ttu-id="8757a-122">Después de publicar los elementos de informe, en el cuadro de diálogo se muestra cuáles se publicaron correctamente y cuáles no.</span><span class="sxs-lookup"><span data-stu-id="8757a-122">After you publish the report parts, the dialog box shows which were successfully published and which were not.</span></span> <span data-ttu-id="8757a-123">En el cuadro de diálogo **Publicar elementos de informe** se muestran los datos de los elementos de informe que no se publicaron.</span><span class="sxs-lookup"><span data-stu-id="8757a-123">You can view details in the **Publish Report Parts** dialog box for the report parts that failed to publish.</span></span>  
  
6.  <span data-ttu-id="8757a-124">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="8757a-124">Click **Close**.</span></span>  
  
### <a name="to-republish-a-report-part"></a><span data-ttu-id="8757a-125">Volver a publicar un elemento de informe</span><span class="sxs-lookup"><span data-stu-id="8757a-125">To republish a report part</span></span>  
  
1.  <span data-ttu-id="8757a-126">Siga el procedimiento anterior de publicación de un elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="8757a-126">Follow the previous procedure for publishing a report part.</span></span>  
  
2.  <span data-ttu-id="8757a-127">En el cuadro de diálogo **Publicar elementos de informe** , si hace clic en **Publicar como una nueva copia del elemento de informe**, el Generador de informes no reemplazará el elemento de informe existente en el servidor, si no que creará otro elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="8757a-127">In the **Publish Report Parts** dialog box, if you click **Publish as a New Copy of the Report Part**, Report Builder will not save over the existing report part on the server, but will create another report part instead.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8757a-128">Si lo publica como nuevo elemento de informe, tendrá un nuevo identificador único.</span><span class="sxs-lookup"><span data-stu-id="8757a-128">If you publish it as a new report part, it will have a new unique ID.</span></span> <span data-ttu-id="8757a-129">Ya no recibirá actualizaciones si cambia el elemento de informe original.</span><span class="sxs-lookup"><span data-stu-id="8757a-129">It will no longer receive updates if the original report part changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8757a-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8757a-130">See Also</span></span>  
 <span data-ttu-id="8757a-131">[Elementos de informe &#40;Generador de informes y SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8757a-131">[Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8757a-132">[Elementos de informe y conjuntos de valores en Generador de informes](../report-data/report-parts-and-datasets-in-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="8757a-132">[Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md) </span></span>  
 <span data-ttu-id="8757a-133">[Solucionar problemas de elementos de informe &#40;Generador de informes y SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8757a-133">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8757a-134">[Buscar actualizaciones o desactivar las actualizaciones de &#40;Generador de informes y SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8757a-134">[Check for Updates or Turn Updates Off &#40;Report Builder and SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8757a-135">Buscar elementos de informe y establecer una carpeta predeterminada &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8757a-135">Browse for Report Parts and Set a Default Folder &#40;Report Builder and SSRS&#41;</span></span>](browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md)  
  
  
