---
title: Cómo ver las propiedades de la instancia CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4bce9b82-7bbd-41df-b3f4-4b40b8bad474
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 86fa298b0e02a16ddbaea220ef7f3d9f6172bf85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746398"
---
# <a name="how-to-view-the-cdc-instance-properties"></a><span data-ttu-id="da058-102">Cómo ver las propiedades de la instancia CDC</span><span class="sxs-lookup"><span data-stu-id="da058-102">How to View the CDC Instance Properties</span></span>
  <span data-ttu-id="da058-103">En este procedimiento se describe cómo usar la consola del Diseñador CDC para ver información acerca de las instancias que se crean para ayudar a administrar el funcionamiento de las instancias.</span><span class="sxs-lookup"><span data-stu-id="da058-103">This procedure describes how to use the CDC Designer Console to view information about the instances that you create to help manage the operation of the instances.</span></span>  
  
### <a name="to-view-information-about-a-specific-instance"></a><span data-ttu-id="da058-104">Para ver información sobre una instancia específica</span><span class="sxs-lookup"><span data-stu-id="da058-104">To view information about a specific instance</span></span>  
  
1.  <span data-ttu-id="da058-105">En el menú **Inicio** , seleccione **Consola del diseñador CDC**.</span><span class="sxs-lookup"><span data-stu-id="da058-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="da058-106">En el panel izquierdo, expanda **Captura de datos modificados** y expanda después el servicio que contiene la instancia que desea ver.</span><span class="sxs-lookup"><span data-stu-id="da058-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance you want to view.</span></span>  
  
3.  <span data-ttu-id="da058-107">Seleccione el nombre de una instancia con la que desee trabajar.</span><span class="sxs-lookup"><span data-stu-id="da058-107">Select the name of an instance you want to work with.</span></span>  
  
     <span data-ttu-id="da058-108">La información sobre la instancia se muestra en la parte central de la Consola del diseñador CDC.</span><span class="sxs-lookup"><span data-stu-id="da058-108">The information about the instance is displayed in the center part of the CDC Designer Console.</span></span> <span data-ttu-id="da058-109">Está dividida en cuatro pestañas.</span><span class="sxs-lookup"><span data-stu-id="da058-109">It is divided into four tabs.</span></span> <span data-ttu-id="da058-110">Todas las pestañas son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="da058-110">All of the tabs are read only.</span></span>  
  
     <span data-ttu-id="da058-111">**Estado**</span><span class="sxs-lookup"><span data-stu-id="da058-111">**Status**</span></span>  
     <span data-ttu-id="da058-112">En esta pestaña se muestra información sobre el estado actual de la captura de datos modificados para la instancia.</span><span class="sxs-lookup"><span data-stu-id="da058-112">This tab displays the information about the current status of the change data capture for the instance.</span></span> <span data-ttu-id="da058-113">Para obtener información acerca de lo que se muestra en esta pestaña, vea la sección **Pestañas del visor** en [Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="da058-113">For information about what is displayed in this tab, see the **Viewer Tabs** section in [Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
     <span data-ttu-id="da058-114">**Oracle**</span><span class="sxs-lookup"><span data-stu-id="da058-114">**Oracle**</span></span>  
     <span data-ttu-id="da058-115">En esta pestaña se muestra información general sobre la instancia CDC y la base de datos de origen de Oracle.</span><span class="sxs-lookup"><span data-stu-id="da058-115">This tab displays general information about the CDC instance and the Oracle source database.</span></span> <span data-ttu-id="da058-116">Para obtener información acerca de lo que se muestra en esta pestaña, vea [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span><span class="sxs-lookup"><span data-stu-id="da058-116">For information about what is displayed in this tab, see [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span></span>  
  
     <span data-ttu-id="da058-117">**Tablas**</span><span class="sxs-lookup"><span data-stu-id="da058-117">**Tables**</span></span>  
     <span data-ttu-id="da058-118">En esta pestaña se muestra información sobre las tablas incluidas en la captura de datos modificados.</span><span class="sxs-lookup"><span data-stu-id="da058-118">This tab displays information about the tables included in the change data capture.</span></span> <span data-ttu-id="da058-119">También se muestran las columnas capturadas.</span><span class="sxs-lookup"><span data-stu-id="da058-119">It also lists the columns that are captured.</span></span> <span data-ttu-id="da058-120">Para obtener información acerca de lo que se muestra en esta pestaña, vea [Edit Tables](edit-tables.md).</span><span class="sxs-lookup"><span data-stu-id="da058-120">For information about what is displayed in this tab, see [Edit Tables](edit-tables.md).</span></span>  
  
     <span data-ttu-id="da058-121">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="da058-121">**Advanced**</span></span>  
     <span data-ttu-id="da058-122">En esta pestaña se muestra una lista de las propiedades avanzadas que define en el editor de propiedades.</span><span class="sxs-lookup"><span data-stu-id="da058-122">This tab displays a list of advanced properties that you define in the properties editor.</span></span> <span data-ttu-id="da058-123">Para obtener información acerca de lo que se muestra en esta pestaña, vea [Edit the Advanced Properties](edit-the-advanced-properties.md).</span><span class="sxs-lookup"><span data-stu-id="da058-123">For information about what is displayed in this tab, see [Edit the Advanced Properties](edit-the-advanced-properties.md).</span></span>  
  
  
