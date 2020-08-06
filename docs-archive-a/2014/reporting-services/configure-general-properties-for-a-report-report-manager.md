---
title: Configurar las propiedades generales de un informe (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], properties
- properties [Reporting Services], general
ms.assetid: 10b941b2-28e6-4408-9ee4-acebc63c8496
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f30900158591afcd5997053dbb61cc22b495ed10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749181"
---
# <a name="configure-general-properties-for-a-report-report-manager"></a><span data-ttu-id="bbb4d-102">Configurar las propiedades generales de un informe (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="bbb4d-102">Configure General Properties for a Report (Report Manager)</span></span>
  
### <a name="to-configure-general-report-properties"></a><span data-ttu-id="bbb4d-103">Para configurar las propiedades generales de un informe</span><span class="sxs-lookup"><span data-stu-id="bbb4d-103">To configure general report properties</span></span>

1.  <span data-ttu-id="bbb4d-104">Inicie el [Administrador de informes &#40;Modo nativo de SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="bbb4d-104">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span></span>

2.  <span data-ttu-id="bbb4d-105">En Administrador de informes, vaya a la página **contenido** .</span><span class="sxs-lookup"><span data-stu-id="bbb4d-105">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="bbb4d-106">Navegue al informe cuyas propiedades generales desea configurar y ábralo.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-106">Navigate to the report that you want to configure general properties for and open it.</span></span>

3.  <span data-ttu-id="bbb4d-107">Haga clic en la pestaña **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-107">Click the **Properties** tab.</span></span>

     <span data-ttu-id="bbb4d-108">O bien, si la página **contenido** está en la vista detalles, haga clic en el icono de la página de propiedades:</span><span class="sxs-lookup"><span data-stu-id="bbb4d-108">Or, if the **Contents** page is in Details view, click the property page icon:</span></span>

     <span data-ttu-id="bbb4d-109">![Icono de la página de propiedades](media/prop.gif "Icono de la página de propiedades")</span><span class="sxs-lookup"><span data-stu-id="bbb4d-109">![Property page icon](media/prop.gif "Property page icon")</span></span>

4.  <span data-ttu-id="bbb4d-110">Se muestra la página propiedades **generales** y puede configurar las propiedades de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="bbb4d-110">The **General** properties page is displayed, and you can configure properties as follows:</span></span>

    -   <span data-ttu-id="bbb4d-111">En la sección **propiedades** , puede modificar el nombre y la descripción del informe.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-111">In the **Properties** section, you can modify the report name and description.</span></span>

    -   <span data-ttu-id="bbb4d-112">Puede activar la casilla **ocultar en la vista de lista** para ocultar el elemento cuando se abre la página en el diseño de página predeterminado (vista de lista), que organiza los elementos en la página.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-112">You can select the **Hide in list view** checkbox to hide the item when the page is opened in the default page layout (list view) which arranges items across and down the page.</span></span>

    -   <span data-ttu-id="bbb4d-113">En la sección **definición de informe** , haga clic en **Editar** para extraer una copia de la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-113">In the **Report Definition** section, click **Edit** to extract a copy of the report definition.</span></span> <span data-ttu-id="bbb4d-114">Las modificaciones que se realizan de manera local en la definición del informe no se guardan en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-114">Modifications that you make locally to the report definition are not saved on the report server.</span></span>

         <span data-ttu-id="bbb4d-115">O bien, para actualizar la definición de informe desde un archivo. RDL, haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-115">Or, to update the report definition from an .rdl file, click **Update**.</span></span>

        > [!NOTE]
        >  <span data-ttu-id="bbb4d-116">Si actualiza una definición de informe, debe restablecer la configuración del origen de datos cuando la actualización haya finalizado.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-116">If you update a report definition, you must reset the data source settings after the update is completed.</span></span>

    -   <span data-ttu-id="bbb4d-117">Use los botones **eliminar** o **movimiento** para eliminar o cambiar el informe.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-117">Use the **Delete** or **Move** buttons to delete or move the report.</span></span>

    -   <span data-ttu-id="bbb4d-118">También puede crear un informe vinculado.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-118">You can also create a linked report.</span></span>

5.  <span data-ttu-id="bbb4d-119">Cuando haya terminado de configurar las propiedades generales del informe, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="bbb4d-119">When you have finished configuring general properties for the report, click **Apply**.</span></span>

## <a name="see-also"></a><span data-ttu-id="bbb4d-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bbb4d-120">See Also</span></span>
 <span data-ttu-id="bbb4d-121">[Mueva o elimine un elemento &#40;administrador de informes página&#41;](report-server/move-or-delete-an-item-report-manager.md) [contenido &#40;administrador de informes](../../2014/reporting-services/contents-page-report-manager.md)&#41;[Buscar, ver y administrar informes &#40;generador de informes y SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) [Página propiedades generales, informes &#40;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="bbb4d-121">[Move or Delete an Item &#40;Report Manager&#41;](report-server/move-or-delete-an-item-report-manager.md) [Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) [Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) [General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md)</span></span>


