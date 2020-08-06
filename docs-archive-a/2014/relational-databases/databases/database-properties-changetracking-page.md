---
title: Propiedades de la base de datos (página ChangeTracking) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.changetracking.f1
ms.assetid: 9b929640-bc62-449b-9b06-b5a77b8cf372
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4107f81ef4cdf19df60d4a70d8e79007f2c9270c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747026"
---
# <a name="database-properties-changetracking-page"></a><span data-ttu-id="ba5fa-102">Propiedades de la base de datos (página ChangeTracking)</span><span class="sxs-lookup"><span data-stu-id="ba5fa-102">Database Properties (ChangeTracking Page)</span></span>
  <span data-ttu-id="ba5fa-103">Utilice esta página para ver o modificar la configuración del seguimiento de cambios de la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ba5fa-103">Use this page to view or modify change tracking settings for the selected database.</span></span> <span data-ttu-id="ba5fa-104">Para obtener más información sobre las opciones disponibles en esta página, vea [Habilitar y deshabilitar el seguimiento de cambios &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba5fa-104">For more information about the options available on this page, see [Enable and Disable Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ba5fa-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="ba5fa-105">Options</span></span>  
 <span data-ttu-id="ba5fa-106">**Seguimiento de cambios**</span><span class="sxs-lookup"><span data-stu-id="ba5fa-106">**Change Tracking**</span></span>  
 <span data-ttu-id="ba5fa-107">Utilice esta opción para habilitar o deshabilitar el seguimiento de cambios de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ba5fa-107">Use to enable or disable change tracking for the database.</span></span>  
  
 <span data-ttu-id="ba5fa-108">Para habilitar el seguimiento de cambios, debe tener el permiso para modificar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ba5fa-108">To enable change tracking, you must have permission to modify the database.</span></span>  
  
 <span data-ttu-id="ba5fa-109">Al cambiar el valor a **True** , se establece una opción de base de datos que permite habilitar el seguimiento en tablas individuales.</span><span class="sxs-lookup"><span data-stu-id="ba5fa-109">Setting the value to **True** sets a database option that allows change tracking to be enabled on individual tables.</span></span>  
  
 <span data-ttu-id="ba5fa-110">También puede configurar el seguimiento de cambios utilizando [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ba5fa-110">You can also configure change tracking by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
 <span data-ttu-id="ba5fa-111">**Período de retención**</span><span class="sxs-lookup"><span data-stu-id="ba5fa-111">**Retention Period**</span></span>  
 <span data-ttu-id="ba5fa-112">Especifica el período mínimo para mantener la información de seguimiento de cambios en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ba5fa-112">Specifies the minimum period for keeping change track information in the database.</span></span> <span data-ttu-id="ba5fa-113">Los datos se quitarán solo si el valor **Limpieza automática**es **True**.</span><span class="sxs-lookup"><span data-stu-id="ba5fa-113">Data is removed only if the **Auto Clean-Up**value is **True**.</span></span>  
  
 <span data-ttu-id="ba5fa-114">El valor predeterminado es 2.</span><span class="sxs-lookup"><span data-stu-id="ba5fa-114">The default value is 2.</span></span>  
  
 <span data-ttu-id="ba5fa-115">**Unidades del período de retención**</span><span class="sxs-lookup"><span data-stu-id="ba5fa-115">**Retention Period Units**</span></span>  
 <span data-ttu-id="ba5fa-116">Especifica las unidades para el valor del Período de retención.</span><span class="sxs-lookup"><span data-stu-id="ba5fa-116">Specifies the units for the Retention Period value.</span></span> <span data-ttu-id="ba5fa-117">Puede seleccionar **Días**, **Horas**o **Minutos**.</span><span class="sxs-lookup"><span data-stu-id="ba5fa-117">You can select **Days**, **Hours**, or **Minutes**.</span></span> <span data-ttu-id="ba5fa-118">El valor predeterminado es **Días**.</span><span class="sxs-lookup"><span data-stu-id="ba5fa-118">The default value is **Days**.</span></span>  
  
 <span data-ttu-id="ba5fa-119">El período de retención mínimo es de 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="ba5fa-119">The minimum retention period is 1 minute.</span></span> <span data-ttu-id="ba5fa-120">No hay ningún período de retención máximo.</span><span class="sxs-lookup"><span data-stu-id="ba5fa-120">There is no maximum retention period.</span></span>  
  
 <span data-ttu-id="ba5fa-121">**Limpieza automática**</span><span class="sxs-lookup"><span data-stu-id="ba5fa-121">**Auto Clean-Up**</span></span>  
 <span data-ttu-id="ba5fa-122">Indica si los datos del seguimiento de cambios se quitan automáticamente después del período de retención especificado.</span><span class="sxs-lookup"><span data-stu-id="ba5fa-122">Indicates whether change tracking information is automatically removed after the specified retention period.</span></span>  
  
 <span data-ttu-id="ba5fa-123">Al habilitar la opción **Limpieza automática** , se restablece cualquier período de retención anterior personalizado al valor predeterminado de 2 días.</span><span class="sxs-lookup"><span data-stu-id="ba5fa-123">Enabling **Auto Clean-Up** resets any previous custom retention period to the default retention period of 2 days.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba5fa-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba5fa-124">See Also</span></span>  
 <span data-ttu-id="ba5fa-125">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba5fa-125">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="ba5fa-126">CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ba5fa-126">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
