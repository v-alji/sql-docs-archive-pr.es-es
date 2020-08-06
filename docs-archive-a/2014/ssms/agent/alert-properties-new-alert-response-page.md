---
title: Propiedades de alerta-nueva alerta (página respuesta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.response.f1
ms.assetid: 72daf008-f9ea-4077-b217-5048e7759d3e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 34e7f11ff3210ec4fc1835751bc35b140d3fa0ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748493"
---
# <a name="alert-properties-new-alert-response-page"></a><span data-ttu-id="6ab06-102">Propiedades de alerta-nueva alerta (página respuesta)</span><span class="sxs-lookup"><span data-stu-id="6ab06-102">Alert Properties-New Alert (Response Page)</span></span>
  <span data-ttu-id="6ab06-103">Utilice esta página para especificar el trabajo que desea ejecutar y para obtener una lista de operadores a los que se notificará en respuesta a una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerta del agente.</span><span class="sxs-lookup"><span data-stu-id="6ab06-103">Use this page to specify a job that you want to run and to obtain a list of operators to be notified in response to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6ab06-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="6ab06-104">Options</span></span>  
 <span data-ttu-id="6ab06-105">**Ejecutar trabajo**</span><span class="sxs-lookup"><span data-stu-id="6ab06-105">**Execute job**</span></span>  
 <span data-ttu-id="6ab06-106">Habilita las opciones **Lista de trabajos**, **Nuevo trabajo** y **Ver trabajo** .</span><span class="sxs-lookup"><span data-stu-id="6ab06-106">Enables the **Job list**, **New job** and **View job** options.</span></span>  
  
 <span data-ttu-id="6ab06-107">**Nuevo trabajo**</span><span class="sxs-lookup"><span data-stu-id="6ab06-107">**New job**</span></span>  
 <span data-ttu-id="6ab06-108">Abre el cuadro de diálogo **Nuevo trabajo** .</span><span class="sxs-lookup"><span data-stu-id="6ab06-108">Open the **New Job** dialog box.</span></span> <span data-ttu-id="6ab06-109">Este botón no está disponible si la opción **Ejecutar trabajo** no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6ab06-109">This button is not available when **Execute job** is not selected.</span></span>  
  
 <span data-ttu-id="6ab06-110">**Ver trabajo**</span><span class="sxs-lookup"><span data-stu-id="6ab06-110">**View job**</span></span>  
 <span data-ttu-id="6ab06-111">Permite ver o modificar el trabajo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6ab06-111">View or modify the selected job.</span></span> <span data-ttu-id="6ab06-112">Esta opción no está disponible si **Ejecutar trabajo** no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6ab06-112">This option is not available when **Execute job** is not selected.</span></span>  
  
 <span data-ttu-id="6ab06-113">**Notificar a los operadores**</span><span class="sxs-lookup"><span data-stu-id="6ab06-113">**Notify operators**</span></span>  
 <span data-ttu-id="6ab06-114">Habilita los controles que le permiten agregar, quitar o cambiar operadores.</span><span class="sxs-lookup"><span data-stu-id="6ab06-114">Enables the controls that allow you to add, remove, or change operators.</span></span>  
  
 <span data-ttu-id="6ab06-115">**Lista de operadores**</span><span class="sxs-lookup"><span data-stu-id="6ab06-115">**Operator list**</span></span>  
 <span data-ttu-id="6ab06-116">Enumera los operadores a los que se notificará cuando se produzca una alerta.</span><span class="sxs-lookup"><span data-stu-id="6ab06-116">Lists the operators to notify when an alert occurs.</span></span> <span data-ttu-id="6ab06-117">Para especificar un método de notificación, seleccione la casilla **Correo electrónico**, **Buscapersonas**o **Net send** que aparece después del nombre del operador. Esta opción no está disponible si **Notificar a los operadores** no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6ab06-117">To specify a notification method, select the **E-mail**, **Pager**, or **Net send** check box that is displayed after the operator name.This option not available when **Notify operators** is not selected.</span></span>  
  
 <span data-ttu-id="6ab06-118">**Por**</span><span class="sxs-lookup"><span data-stu-id="6ab06-118">**E-mail**</span></span>  
 <span data-ttu-id="6ab06-119">Utiliza el correo electrónico para notificar al operador.</span><span class="sxs-lookup"><span data-stu-id="6ab06-119">Use e-mail to notify the operator.</span></span>  
  
 <span data-ttu-id="6ab06-120">**Buscapersonas**</span><span class="sxs-lookup"><span data-stu-id="6ab06-120">**Pager**</span></span>  
 <span data-ttu-id="6ab06-121">Utiliza la dirección de correo electrónico del buscapersonas para notificar al operador.</span><span class="sxs-lookup"><span data-stu-id="6ab06-121">Use the pager e-mail address to notify the operator.</span></span>  
  
 <span data-ttu-id="6ab06-122">**Net send**</span><span class="sxs-lookup"><span data-stu-id="6ab06-122">**Net send**</span></span>  
 <span data-ttu-id="6ab06-123">Use **net send** para notificar al operador.</span><span class="sxs-lookup"><span data-stu-id="6ab06-123">Use **net send** to notify the operator.</span></span>  
  
 <span data-ttu-id="6ab06-124">**New (operador)**</span><span class="sxs-lookup"><span data-stu-id="6ab06-124">**New operator**</span></span>  
 <span data-ttu-id="6ab06-125">Muestra el cuadro de diálogo **Nuevo operador** , que se puede usar para crear un nuevo operador.</span><span class="sxs-lookup"><span data-stu-id="6ab06-125">Displays the **New Operator** dialog box, which you can use to create a new operator.</span></span>  
  
 <span data-ttu-id="6ab06-126">**Ver operador**</span><span class="sxs-lookup"><span data-stu-id="6ab06-126">**View operator**</span></span>  
 <span data-ttu-id="6ab06-127">Muestra el cuadro de diálogo **Propiedades** para el operador seleccionado actualmente.</span><span class="sxs-lookup"><span data-stu-id="6ab06-127">Displays the **Properties** dialog box for the currently selected operator.</span></span> <span data-ttu-id="6ab06-128">Puede ver y modificar las propiedades del operador en el cuadro de diálogo **Propiedades del operador**.</span><span class="sxs-lookup"><span data-stu-id="6ab06-128">You can view and modified operator properties on the **Operator Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ab06-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ab06-129">See Also</span></span>  
 <span data-ttu-id="6ab06-130">[Alerts](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="6ab06-130">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="6ab06-131">[Crear una alerta con nivel de gravedad](create-an-alert-using-severity-level.md) </span><span class="sxs-lookup"><span data-stu-id="6ab06-131">[Create an Alert Using Severity Level](create-an-alert-using-severity-level.md) </span></span>  
 <span data-ttu-id="6ab06-132">[Alerts](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="6ab06-132">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="6ab06-133">[Editar una alerta](edit-an-alert.md) </span><span class="sxs-lookup"><span data-stu-id="6ab06-133">[Edit an Alert](edit-an-alert.md) </span></span>  
 [<span data-ttu-id="6ab06-134">Delete an Alert</span><span class="sxs-lookup"><span data-stu-id="6ab06-134">Delete an Alert</span></span>](delete-an-alert.md)  
  
  
