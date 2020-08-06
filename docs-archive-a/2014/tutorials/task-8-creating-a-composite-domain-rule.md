---
title: 'Tarea 8: crear una regla de dominio compuesto | Microsoft Docs'
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: cff3b662-7876-4445-9bdd-96be35b3ca0c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4766a1206eb09e98bb20d3712a63762126b682b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675682"
---
# <a name="task-8-creating-a-composite-domain-rule"></a><span data-ttu-id="7684c-102">Tarea 8: Creación de una regla de dominio compuesto</span><span class="sxs-lookup"><span data-stu-id="7684c-102">Task 8: Creating a Composite Domain Rule</span></span>
  <span data-ttu-id="7684c-103">En esta tarea, creará una regla para el dominio compuesto **validación de direcciones** .</span><span class="sxs-lookup"><span data-stu-id="7684c-103">In this task, you create a rule for the **Address Validation** composite domain.</span></span> <span data-ttu-id="7684c-104">Defina una regla entre dominios: Si **City** es los **Ángeles**, el **Estado** debe ser **CA** , donde la **ciudad** y el **Estado** son dos dominios.</span><span class="sxs-lookup"><span data-stu-id="7684c-104">You define a cross-domain rule: if **City** is **Los Angeles**, **State** must be **CA** where **City** and **State** are two domains.</span></span>  
  
1.  <span data-ttu-id="7684c-105">En el panel derecho, cambie a la pestaña **reglas de CD** .</span><span class="sxs-lookup"><span data-stu-id="7684c-105">In the right pane, switch to the **CD Rules** tab.</span></span>  
  
2.  <span data-ttu-id="7684c-106">Haga clic en **Agregar una nueva regla de dominio** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="7684c-106">Click **Add a new domain rule** from the toolbar.</span></span>  
  
3.  <span data-ttu-id="7684c-107">Escriba **City: regla de estado** para **nombre** y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="7684c-107">Type **City-State Rule** for **Name** and press **ENTER**.</span></span>  
  
4.  <span data-ttu-id="7684c-108">En el panel **generar una regla** , seleccione **ciudad** en la lista de dominios y seleccione el valor de la condición **es igual a** y escriba los **Ángeles** para el valor.</span><span class="sxs-lookup"><span data-stu-id="7684c-108">In the **Build a Rule** pane, select **City** in the domain list, and select condition **Value is equal to** and type **Los Angeles** for the value.</span></span>  
  
5.  <span data-ttu-id="7684c-109">En el panel **then** , seleccione **Estado** en la lista de dominios y seleccione el **valor es igual a**, escriba **CA** como valor y presione **Tab**.</span><span class="sxs-lookup"><span data-stu-id="7684c-109">In the **Then** pane, select **State** in the domain list, and select **Value is equal to**, type **CA** for the value, and press **TAB**.</span></span>  
  
     <span data-ttu-id="7684c-110">![Regla de dominio compuesto](../../2014/tutorials/media/et-creatingacompositedomainrule.jpg "Regla de dominio compuesto")</span><span class="sxs-lookup"><span data-stu-id="7684c-110">![Composite Domain Rule](../../2014/tutorials/media/et-creatingacompositedomainrule.jpg "Composite Domain Rule")</span></span>  
  
6.  <span data-ttu-id="7684c-111">Haga clic en el botón **cerrar** situado en la parte inferior de la página para cambiar a la Página principal del cliente DQS.</span><span class="sxs-lookup"><span data-stu-id="7684c-111">Click **Close** button at the bottom of the page to switch to the main page of DQS Client.</span></span> <span data-ttu-id="7684c-112">Publicará la base de conocimiento en la próxima lección.</span><span class="sxs-lookup"><span data-stu-id="7684c-112">You will publish the knowledge base in the next lesson.</span></span> <span data-ttu-id="7684c-113">Observe que la base de conocimiento está en estado bloqueado (icono de candado).</span><span class="sxs-lookup"><span data-stu-id="7684c-113">Notice that the knowledge base is in locked state (lock icon).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="7684c-114">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="7684c-114">Next Step</span></span>  
 [<span data-ttu-id="7684c-115">Tarea 9: Configuración de un servicio de datos de referencia</span><span class="sxs-lookup"><span data-stu-id="7684c-115">Task 9: Configuring a Reference Data Service</span></span>](../../2014/tutorials/task-9-configuring-a-reference-data-service.md)  
  
  
