---
title: Crear un informe vinculado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- linked reports [Reporting Services], creating
ms.assetid: 12be8341-cb57-45e8-a421-2bf66b50234d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed5e70c9ff8179ae05186685e21303693fc9aed7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674563"
---
# <a name="create-a-linked-report"></a><span data-ttu-id="350da-102">Crear un informe vinculado</span><span class="sxs-lookup"><span data-stu-id="350da-102">Create a Linked Report</span></span>
  <span data-ttu-id="350da-103">Un informe vinculado es un elemento del servidor de informes que proporciona un punto de acceso a un informe existente.</span><span class="sxs-lookup"><span data-stu-id="350da-103">A linked report is a report server item that provides an access point to an existing report.</span></span> <span data-ttu-id="350da-104">Conceptualmente, es similar a los accesos directos a programa que se usan para ejecutar un programa o abrir un archivo.</span><span class="sxs-lookup"><span data-stu-id="350da-104">Conceptually, it is similar to a program shortcut that you use to run a program or open a file.</span></span>

 <span data-ttu-id="350da-105">Un informe vinculado se deriva de otro informe existente y conserva la definición de informe original.</span><span class="sxs-lookup"><span data-stu-id="350da-105">A linked report is derived from an existing report and retains the original's report definition.</span></span> <span data-ttu-id="350da-106">El informe vinculado siempre hereda el diseño de informe y las propiedades del origen de datos del informe original.</span><span class="sxs-lookup"><span data-stu-id="350da-106">A linked report always inherits report layout and data source properties of the original report.</span></span> <span data-ttu-id="350da-107">El resto de propiedades y parámetros pueden ser distintos de los del informe original, incluyendo la seguridad, los parámetros, la ubicación, las suscripciones y las programaciones.</span><span class="sxs-lookup"><span data-stu-id="350da-107">All other properties and settings can be different from those of the original report, including security, parameters, location, subscriptions, and schedules.</span></span>

 <span data-ttu-id="350da-108">Se puede crear un informe vinculado cuando se desean crear versiones adicionales de un informe existente.</span><span class="sxs-lookup"><span data-stu-id="350da-108">You can create a linked report when you want to create additional versions of an existing report.</span></span> <span data-ttu-id="350da-109">Por ejemplo, se podría usar un único informe de ventas regional para crear informes específicos de regiones para todos los territorios de ventas.</span><span class="sxs-lookup"><span data-stu-id="350da-109">For example, you could use a single regional sales report to create region-specific reports for all of your sales territories.</span></span>

 <span data-ttu-id="350da-110">Si bien los informes vinculados se basan normalmente en informes con parámetros, no es necesario disponer de este tipo de informe.</span><span class="sxs-lookup"><span data-stu-id="350da-110">Although linked reports are typically based on parameterized reports, a parameterized report is not required.</span></span> <span data-ttu-id="350da-111">Puede crear informes vinculados siempre que desee implementar un informe existente con diferentes parámetros.</span><span class="sxs-lookup"><span data-stu-id="350da-111">You can create linked reports whenever you want to deploy an existing report with different settings.</span></span>

### <a name="to-create-a-linked-report"></a><span data-ttu-id="350da-112">Crear un informe vinculado</span><span class="sxs-lookup"><span data-stu-id="350da-112">To create a linked report</span></span>

1.  <span data-ttu-id="350da-113">En el Administrador de informes, navegue hasta la carpeta que contiene el informe al que desea vincular y, a continuación, abra el menú de opciones para hacer clic en **Crear informe vinculado**.</span><span class="sxs-lookup"><span data-stu-id="350da-113">In Report Manager, navigate to the folder containing the report that you want to link to, and then open the options menu can click **Create Linked Report**.</span></span>

2.  <span data-ttu-id="350da-114">Escriba un nombre para el nuevo informe vinculado.</span><span class="sxs-lookup"><span data-stu-id="350da-114">Type a name for the new linked report.</span></span> <span data-ttu-id="350da-115">Si lo desea, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="350da-115">Optionally type a description.</span></span>

3.  <span data-ttu-id="350da-116">Para guardar el informe en una carpeta diferente, haga clic en **Cambiar ubicación**.</span><span class="sxs-lookup"><span data-stu-id="350da-116">To select a different folder for the report, click **Change Location**.</span></span> <span data-ttu-id="350da-117">Haga clic en la carpeta que desee utilizar o escriba el nombre de la carpeta en el cuadro **Ubicación** .</span><span class="sxs-lookup"><span data-stu-id="350da-117">Click the folder you want to use, or type the folder name in the **Location** box.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)] <span data-ttu-id="350da-118">Si no selecciona una carpeta distinta, el informe vinculado se creará en la carpeta actual (donde está almacenado el informe en que se basa).</span><span class="sxs-lookup"><span data-stu-id="350da-118">If you do not select a different folder, the linked report is created in the current folder (where the report it is based on is stored).</span></span>

4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)] <span data-ttu-id="350da-119">Se abre el informe vinculado.</span><span class="sxs-lookup"><span data-stu-id="350da-119">The linked report opens.</span></span>

     <span data-ttu-id="350da-120">El icono de un informe vinculado es distinto de otros elementos administrados por un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="350da-120">A linked report's icon differs from other items managed by a report server.</span></span> <span data-ttu-id="350da-121">El siguiente icono distingue los informes vinculados:</span><span class="sxs-lookup"><span data-stu-id="350da-121">The following icon indicates a linked report:</span></span>

     <span data-ttu-id="350da-122">![Icono de informe vinculado](../media/hlp-16linked.gif "Icono de informe vinculado")</span><span class="sxs-lookup"><span data-stu-id="350da-122">![Linked report icon](../media/hlp-16linked.gif "Linked report icon")</span></span>

## <a name="see-also"></a><span data-ttu-id="350da-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="350da-123">See Also</span></span>
 <span data-ttu-id="350da-124">[Abrir y cerrar un informe &#40;Administrador de informes&#41;](../reports/open-and-close-a-report-report-manager.md) [Página nuevo informe vinculado &#40;administrador de informes&#41;](../new-linked-report-page-report-manager.md) [Elegir ubicación del elemento &#40;](../choose-item-location-page-report-manager.md) administrador de informes&#41;[Página propiedades generales, informes &#40;](../general-properties-page-reports-report-manager.md) administrador de informes&#41;Reporting Services [conceptos &#40;SSRS&#41;](../reporting-services-concepts-ssrs.md) administrador de informes &#40;el [modo nativo de SSRS](../report-manager-ssrs-native-mode.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="350da-124">[Open and Close a Report &#40;Report Manager&#41;](../reports/open-and-close-a-report-report-manager.md) [New Linked Report Page &#40;Report Manager&#41;](../new-linked-report-page-report-manager.md) [Choose Item Location Page &#40;Report Manager&#41;](../choose-item-location-page-report-manager.md) [General Properties Page, Reports &#40;Report Manager&#41;](../general-properties-page-reports-report-manager.md) [Reporting Services Concepts &#40;SSRS&#41;](../reporting-services-concepts-ssrs.md) [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md)</span></span>


