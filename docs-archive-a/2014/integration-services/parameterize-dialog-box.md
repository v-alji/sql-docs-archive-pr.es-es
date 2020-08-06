---
title: Parametrizar (cuadro de diálogo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.parameter.f1
ms.assetid: fac02b6d-d247-447a-8940-e8700c7ac350
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8db19844132402740aec092d6e88f3c9e3864d58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673077"
---
# <a name="parameterize-dialog-box"></a><span data-ttu-id="b516e-102">Parameterize Dialog Box</span><span class="sxs-lookup"><span data-stu-id="b516e-102">Parameterize Dialog Box</span></span>
  <span data-ttu-id="b516e-103">El cuadro de diálogo **Parametrizar** permite asociar un parámetro nuevo o existente con una propiedad de una tarea.</span><span class="sxs-lookup"><span data-stu-id="b516e-103">The **Parameterize** dialog box enables you to associate a new or an existing parameter with a property of a task.</span></span> <span data-ttu-id="b516e-104">Abra el cuadro de diálogo haciendo clic con el botón secundario en una tarea o en la pestaña Flujo de control en el Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] y haciendo clic en **Parametrizar**.</span><span class="sxs-lookup"><span data-stu-id="b516e-104">You open the dialog box by right-clicking a task or the Control Flow tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer and then by clicking **Parameterize**.</span></span> <span data-ttu-id="b516e-105">La siguiente lista describe los elementos de la interfaz de usuario en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b516e-105">The following list describes UI elements in the dialog box.</span></span> <span data-ttu-id="b516e-106">Para más información sobre los parámetros, vea [Parámetros de Integration Services &#40;SSIS&#41;](integration-services-ssis-package-and-project-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="b516e-106">For more information about parameters, see [Integration Services &#40;SSIS&#41; Parameters](integration-services-ssis-package-and-project-parameters.md).</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="b516e-107">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="b516e-107">UI element list</span></span>  
 <span data-ttu-id="b516e-108">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="b516e-108">**Property**</span></span>  
 <span data-ttu-id="b516e-109">Seleccione la propiedad de la tarea que desea asociar con un parámetro.</span><span class="sxs-lookup"><span data-stu-id="b516e-109">Select the property of the task that you want to associate with a parameter.</span></span> <span data-ttu-id="b516e-110">Esta lista se rellena con todas las propiedades que se pueden utilizar con parámetros.</span><span class="sxs-lookup"><span data-stu-id="b516e-110">This list is populated with all the properties that can be parameterized.</span></span>  
  
 <span data-ttu-id="b516e-111">**Usar parámetros existentes**</span><span class="sxs-lookup"><span data-stu-id="b516e-111">**Use existing parameter**</span></span>  
 <span data-ttu-id="b516e-112">Seleccione esta opción para asociar la propiedad de tarea con un parámetro existente y, a continuación, seleccione el parámetro de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b516e-112">Select this option to associate the property of task with an existing parameter and then select the parameter from drop-down list.</span></span>  
  
 <span data-ttu-id="b516e-113">**No use parámetros**</span><span class="sxs-lookup"><span data-stu-id="b516e-113">**Do not use parameter**</span></span>  
 <span data-ttu-id="b516e-114">Seleccione esta opción para quitar una referencia a un parámetro.</span><span class="sxs-lookup"><span data-stu-id="b516e-114">Select this option to remove a reference to a parameter.</span></span> <span data-ttu-id="b516e-115">Parámetro no se elimina.</span><span class="sxs-lookup"><span data-stu-id="b516e-115">The parameter is not deleted.</span></span>  
  
 <span data-ttu-id="b516e-116">**Crear nuevo parámetro**</span><span class="sxs-lookup"><span data-stu-id="b516e-116">**Create new parameter**</span></span>  
 <span data-ttu-id="b516e-117">Seleccione esta opción para crear un nuevo parámetro que desee asociar con la propiedad de tarea.</span><span class="sxs-lookup"><span data-stu-id="b516e-117">Select this option to create a new parameter that you want to associate with the property of the task.</span></span>  
  
 <span data-ttu-id="b516e-118">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="b516e-118">**Name**</span></span>  
 <span data-ttu-id="b516e-119">Especifique el nombre del parámetro que desea crear.</span><span class="sxs-lookup"><span data-stu-id="b516e-119">Specify the name of the parameter you want to create.</span></span>  
  
 <span data-ttu-id="b516e-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b516e-120">**Description**</span></span>  
 <span data-ttu-id="b516e-121">Especifique la descripción del parámetro.</span><span class="sxs-lookup"><span data-stu-id="b516e-121">Specify the description for parameter.</span></span>  
  
 <span data-ttu-id="b516e-122">**Valor**</span><span class="sxs-lookup"><span data-stu-id="b516e-122">**Value**</span></span>  
 <span data-ttu-id="b516e-123">Especifique el valor predeterminado del parámetro.</span><span class="sxs-lookup"><span data-stu-id="b516e-123">Specify the default value for the parameter.</span></span> <span data-ttu-id="b516e-124">Se conoce también como valor predeterminado de diseño, el cual se puede invalidar más adelante durante la fase de implementación.</span><span class="sxs-lookup"><span data-stu-id="b516e-124">This is also known as the design default, which can be overridden later at the deployment time.</span></span>  
  
 <span data-ttu-id="b516e-125">**Ámbito**</span><span class="sxs-lookup"><span data-stu-id="b516e-125">**Scope**</span></span>  
 <span data-ttu-id="b516e-126">Especifique el ámbito del parámetro seleccionando la opción **Proyecto** o **Paquete** .</span><span class="sxs-lookup"><span data-stu-id="b516e-126">Specify the scope of the parameter by selecting either **Project** or **Package** option.</span></span> <span data-ttu-id="b516e-127">Los parámetros de proyecto se usan para proporcionar cualquier entrada externa que el proyecto recibe a uno o más paquetes del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b516e-127">Project parameters are used to supply any external input the project receives to one or more packages in the project.</span></span> <span data-ttu-id="b516e-128">Los parámetros de paquete permiten modificar la ejecución del paquete sin tener que modificarlo ni volver a implementarlo.</span><span class="sxs-lookup"><span data-stu-id="b516e-128">Package parameters allow you to modify package execution without having to edit and redeploy the package.</span></span>  
  
 <span data-ttu-id="b516e-129">**Sensibilidad**</span><span class="sxs-lookup"><span data-stu-id="b516e-129">**Sensitive**</span></span>  
 <span data-ttu-id="b516e-130">Especifique si es un parámetro con distinción activando o desactivando la casilla.</span><span class="sxs-lookup"><span data-stu-id="b516e-130">Specify whether the parameter is a sensitive by checking or clearing the check box.</span></span> <span data-ttu-id="b516e-131">Los valores de parámetros con distinción se cifran en el catálogo y aparecen como valor NULL cuando se ven con Transact-SQL o SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="b516e-131">Sensitive parameter values are encrypted in the catalog and appear as a NULL value when viewed with Transact-SQL or SQL Server Management Studio.</span></span>  
  
 <span data-ttu-id="b516e-132">**Obligatorio**</span><span class="sxs-lookup"><span data-stu-id="b516e-132">**Required**</span></span>  
 <span data-ttu-id="b516e-133">Especifique si el parámetro requiere que se especifique un valor, distinto del valor predeterminado de diseño, antes de que el paquete se ejecute.</span><span class="sxs-lookup"><span data-stu-id="b516e-133">Specify whether the parameter requires that a value, other than the design default, is specified before the package can execute.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="b516e-134">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="b516e-134">UI element list</span></span>  
  
