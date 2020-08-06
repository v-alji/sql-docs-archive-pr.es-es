---
title: Cómo editar las propiedades de la instancia de CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7a6c719a-3735-43b7-b3ab-dfadd325eca2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b02785a32fa1f64d5da0c3202acd7916da1e65ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744262"
---
# <a name="how-to-edit-the-cdc-instance-properties"></a><span data-ttu-id="92890-102">Cómo editar las propiedades de la instancia CDC</span><span class="sxs-lookup"><span data-stu-id="92890-102">How to Edit the CDC Instance Properties</span></span>
  <span data-ttu-id="92890-103">En este procedimiento se describe cómo usar la Consola del diseñador CDC para editar las propiedades de configuración de una instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="92890-103">This procedure describes how to use the CDC Designer Console to edit the configuration properties for a CDC instance.</span></span>  
  
### <a name="to-edit-the-cdc-instance-configuration-properties"></a><span data-ttu-id="92890-104">Para editar las propiedades de configuración de la instancia CDC</span><span class="sxs-lookup"><span data-stu-id="92890-104">To edit the CDC instance configuration properties</span></span>  
  
1.  <span data-ttu-id="92890-105">En el menú **Inicio** , seleccione **Consola del diseñador CDC**.</span><span class="sxs-lookup"><span data-stu-id="92890-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="92890-106">En el panel izquierdo, expanda **Captura de datos modificados** y expanda después el servicio que contiene la instancia cuyas propiedades desea editar.</span><span class="sxs-lookup"><span data-stu-id="92890-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance with the properties that you want to edit.</span></span>  
  
3.  <span data-ttu-id="92890-107">Seleccione el nombre de la instancia cuyas propiedades desea editar.</span><span class="sxs-lookup"><span data-stu-id="92890-107">Select the name of the instance where you want to edit the properties.</span></span>  
  
4.  <span data-ttu-id="92890-108">En el panel Acciones situado en el lado derecho de la Consola del diseñador CDC, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="92890-108">From the Actions pane on the right side of the CDC Designer Console, click **Properties**.</span></span>  
  
     <span data-ttu-id="92890-109">También puede hacer clic con el botón derecho en la instancia cuyas propiedades quiere editar y luego hacer clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="92890-109">You can also right-click the instance where you want to edit the properties and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="92890-110">En el editor de propiedades, edite las propiedades en las pestañas siguientes:</span><span class="sxs-lookup"><span data-stu-id="92890-110">In the Properties editor, edit the properties in the following tabs:</span></span>  
  
    -   <span data-ttu-id="92890-111">**Oracle**: use la pestaña **Oracle** del editor de propiedades para realizar cambios en la descripción que proporcionó en la página Crear base de datos CDC del Asistente para nueva instancia y para realizar cambios en la información de conexión a bases de datos de Oracle Log Mining.</span><span class="sxs-lookup"><span data-stu-id="92890-111">**Oracle**: Use the **Oracle** tab in the Properties editor to make changes to the description you provided in the Create CDC database page in the New Instance wizard and to make changes to the Oracle Log Mining database connection information.</span></span>  
  
         <span data-ttu-id="92890-112">Para obtener información acerca de lo que puede editar en esta pestaña, vea [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span><span class="sxs-lookup"><span data-stu-id="92890-112">For information about what you can edit in this tab, see [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span></span>  
  
    -   <span data-ttu-id="92890-113">**Tablas**: use la pestaña **Tablas** para realizar cambios en las tablas y columnas que seleccionó en la base de datos de origen de Oracle.</span><span class="sxs-lookup"><span data-stu-id="92890-113">**Tables**: Use the **Tables** tab to make changes to the tables and columns that you selected from the Oracle source database.</span></span>  
  
         <span data-ttu-id="92890-114">Para obtener información acerca de lo que puede editar en esta pestaña, vea [Edit Tables](edit-tables.md).</span><span class="sxs-lookup"><span data-stu-id="92890-114">For information about what you can edit in this tab, see Edit [Edit Tables](edit-tables.md)</span></span>  
  
    -   <span data-ttu-id="92890-115">**Scripts**: use la pestaña **Scripts** para ejecutar o volver a ejecutar un script en la base de datos de origen de Oracle que configurará el registro complementario.</span><span class="sxs-lookup"><span data-stu-id="92890-115">**Scripts**: Use the **Scripts** tab to run or re-run a script on the Oracle source database that will set up supplemental logging.</span></span>  
  
         <span data-ttu-id="92890-116">Para obtener información acerca de lo que puede hacer en esta pestaña, vea [Review and Generate Supplemental Logging Scripts](review-and-generate-supplemental-logging-scripts.md).</span><span class="sxs-lookup"><span data-stu-id="92890-116">For information about what you can do in this tab, see [Review and Generate Supplemental Logging Scripts](review-and-generate-supplemental-logging-scripts.md).</span></span>  
  
    -   <span data-ttu-id="92890-117">**Avanzadas**: use la pestaña **Avanzadas** para agregar propiedades especiales a la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="92890-117">**Advanced**: Use the **Advanced** tab to add special properties to the CDC instance.</span></span>  
  
         <span data-ttu-id="92890-118">Para obtener información acerca de lo que puede hacer en esta pestaña, vea [Edit the Advanced Properties](edit-the-advanced-properties.md).</span><span class="sxs-lookup"><span data-stu-id="92890-118">For information about what you can do in this tab, see [Edit the Advanced Properties](edit-the-advanced-properties.md).</span></span>  
  
  
