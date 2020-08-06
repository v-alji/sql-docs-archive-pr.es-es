---
title: Realizar cambios en las tablas seleccionadas para capturar cambios | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- makChanToTab
ms.assetid: a309f82a-c6ef-464d-a6ef-df555bfb609a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 258eb8e761ac697bebd630cc0e627941b4ffc7d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670508"
---
# <a name="make-changes-to-the-tables-selected-for-capturing-changes"></a><span data-ttu-id="cac2e-102">Realizar cambios en las tablas seleccionadas para capturar cambios</span><span class="sxs-lookup"><span data-stu-id="cac2e-102">Make Changes to the Tables Selected for Capturing Changes</span></span>
  <span data-ttu-id="cac2e-103">En este cuadro de diálogo, puede seleccionar determinadas columnas de la tabla seleccionada desde las que se van a capturar datos.</span><span class="sxs-lookup"><span data-stu-id="cac2e-103">In this dialog box, you can select specific columns from the selected table to capture changes from.</span></span> <span data-ttu-id="cac2e-104">También puede editar la información de **Rol de seguridad** y de **Instancia de captura** .</span><span class="sxs-lookup"><span data-stu-id="cac2e-104">You can also edit the **Security Role** and **Capture Instance** information.</span></span>  
  
 <span data-ttu-id="cac2e-105">Puede realizar los cambios siguientes en las tablas seleccionadas para capturar cambios en este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cac2e-105">You can make the following changes to the tables you selected for capturing changes in this dialog box.</span></span>  
  
 <span data-ttu-id="cac2e-106">**Realizar cambios a las columnas incluidas en la instancia CDC:**</span><span class="sxs-lookup"><span data-stu-id="cac2e-106">**Make changes to which columns are included in the CDC instance:**</span></span>  
  
 <span data-ttu-id="cac2e-107">Realice una o ambas de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="cac2e-107">Do one or both of the following:</span></span>  
  
-   <span data-ttu-id="cac2e-108">Active la casilla situada junto a cualquier columna adicional que desee incluir.</span><span class="sxs-lookup"><span data-stu-id="cac2e-108">Select the check box next to any additional column you want to include.</span></span>  
  
-   <span data-ttu-id="cac2e-109">Desactive la casilla situada junto a cualquier columna que ya no desee incluir.</span><span class="sxs-lookup"><span data-stu-id="cac2e-109">Clear the check box next to any column that you no longer want to include.</span></span>  
  
 <span data-ttu-id="cac2e-110">**Cambiar el tipo de datos para una columna específica**:</span><span class="sxs-lookup"><span data-stu-id="cac2e-110">**Change the data type for a specific column**:</span></span>  
  
 <span data-ttu-id="cac2e-111">Puede seleccionar un tipo de datos diferente para una columna determinada.</span><span class="sxs-lookup"><span data-stu-id="cac2e-111">You can select a different data type for a specific column.</span></span> <span data-ttu-id="cac2e-112">Solo puede cambiar el tipo de datos a uno que sea compatible con el tipo de datos original.</span><span class="sxs-lookup"><span data-stu-id="cac2e-112">You can only change the data type to a data type that is compatible with the original data type.</span></span>  
  
 <span data-ttu-id="cac2e-113">Para cambiar el tipo de datos, haga clic en la columna **Tipo de datos** y seleccione un tipo de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="cac2e-113">To change the data type, click in the **Data Type** column and select a different data type.</span></span> <span data-ttu-id="cac2e-114">Solo están disponibles los tipos de datos compatibles con el tipo de datos original.</span><span class="sxs-lookup"><span data-stu-id="cac2e-114">Only data types that are compatible with the original data type are available.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cac2e-115">Si no se puede seleccionar ningún tipo de datos adicional, la lista desplegable no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="cac2e-115">If no additional data types can be selected, the drop-down list is not available.</span></span>  
  
 <span data-ttu-id="cac2e-116">**Cambiar el rol de seguridad**</span><span class="sxs-lookup"><span data-stu-id="cac2e-116">**Change the Security Role**</span></span>  
  
 <span data-ttu-id="cac2e-117">Escriba un nuevo nombre o edite el nombre del rol de acceso de seguridad en el campo **Rol de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="cac2e-117">Type a new name or edit the name of the security gating role in the **Security Role** field.</span></span>  
  
 <span data-ttu-id="cac2e-118">**Cambiar o agregar una instancia de captura**</span><span class="sxs-lookup"><span data-stu-id="cac2e-118">**Change or add a capture instance**</span></span>  
  
 <span data-ttu-id="cac2e-119">En el campo **Instancia de captura** , escriba un nombre para la instancia de captura.</span><span class="sxs-lookup"><span data-stu-id="cac2e-119">In the **Capture Instance** field enter a name for the capture instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac2e-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cac2e-120">See Also</span></span>  
 <span data-ttu-id="cac2e-121">[Cómo crear la instancia de base de datos de cambios de SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="cac2e-121">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="cac2e-122">Seleccione las columnas y tablas de Oracle </span><span class="sxs-lookup"><span data-stu-id="cac2e-122">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
