---
title: 'Tarea 7: crear un dominio compuesto | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: ae778647-1df0-4952-9a69-0ef6177eea9c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42936d25e267bcad5ba8ae512750f9e12f041579
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662397"
---
# <a name="task-7-creating-a-composite-domain"></a><span data-ttu-id="2e20c-102">Tarea 7: Creación de un dominio compuesto</span><span class="sxs-lookup"><span data-stu-id="2e20c-102">Task 7: Creating a Composite Domain</span></span>
  <span data-ttu-id="2e20c-103">En esta tarea, creará un dominio compuesto, **la validación de direcciones**, que comprende los dominios de línea de **Dirección**, **ciudad**, **Estado**y **código postal** .</span><span class="sxs-lookup"><span data-stu-id="2e20c-103">In this task, you create a composite domain, **Address Validation**, which comprises **Address Line**, **City**, **State**, and **Zip** domains.</span></span> <span data-ttu-id="2e20c-104">Un dominio compuesto permite definir una regla entre dominios que afecta a varias dominios de una regla.</span><span class="sxs-lookup"><span data-stu-id="2e20c-104">A composite domain lets you define a cross-domain rule that involves multiple domains in a rule.</span></span> <span data-ttu-id="2e20c-105">Un dominio compuesto presenta otras ventajas como la posibilidad de analizar un valor de campo en varios dominios.</span><span class="sxs-lookup"><span data-stu-id="2e20c-105">There are other advantages to a composite domain such as being able to parse a field value into multiple domains.</span></span>  <span data-ttu-id="2e20c-106">Por ejemplo, un valor de un campo Nombre completo se puede analizar en distintos dominios Nombre, Segundo nombre y Apellidos.</span><span class="sxs-lookup"><span data-stu-id="2e20c-106">For example, a value for a Full Name field can be parsed into separate First Name, Middle Name, and Last Name domains.</span></span> <span data-ttu-id="2e20c-107">En este tutorial, solo definirá una regla entre dominios.</span><span class="sxs-lookup"><span data-stu-id="2e20c-107">In this tutorial, you only define a cross-domain rule.</span></span> <span data-ttu-id="2e20c-108">Vea [administrar un dominio compuesto](https://msdn.microsoft.com/library/hh510399.aspx) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="2e20c-108">See [Managing a Composite Domain](https://msdn.microsoft.com/library/hh510399.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="2e20c-109">En el panel izquierdo, haga clic en el botón **crear un dominio compuesto** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="2e20c-109">In the left pane, click **Create a composite domain** button on the toolbar.</span></span>  
  
     <span data-ttu-id="2e20c-110">![Botón de barra de herramientas Crear un dominio compuesto](../../2014/tutorials/media/et-creatingacompositedomain-01.jpg "Botón de barra de herramientas Crear un dominio compuesto")</span><span class="sxs-lookup"><span data-stu-id="2e20c-110">![Create a Composite Domain Toolbar Button](../../2014/tutorials/media/et-creatingacompositedomain-01.jpg "Create a Composite Domain Toolbar Button")</span></span>  
  
2.  <span data-ttu-id="2e20c-111">Escriba la **validación de direcciones** para el nombre de **dominio compuesto**.</span><span class="sxs-lookup"><span data-stu-id="2e20c-111">Enter **Address Validation** for the **Composite Domain Name**.</span></span>  
  
     <span data-ttu-id="2e20c-112">![Dominio compuesto de validación de direcciones](../../2014/tutorials/media/et-creatingacompositedomain-02.jpg "Dominio compuesto de validación de direcciones")</span><span class="sxs-lookup"><span data-stu-id="2e20c-112">![Address Validation Composite Domain](../../2014/tutorials/media/et-creatingacompositedomain-02.jpg "Address Validation Composite Domain")</span></span>  
  
3.  <span data-ttu-id="2e20c-113">En la lista de dominios, seleccione **línea de dirección**, **ciudad**, **Estado**y **código postal** y haga clic en la **flecha derecha** para agregarlos a la lista **dominios en el dominio compuesto** .</span><span class="sxs-lookup"><span data-stu-id="2e20c-113">From the domain list select **Address Line**, **City**, **State**, and **Zip** and click **right arrow** to add them to the **Domains in Composite Domain** list.</span></span>  
  
4.  <span data-ttu-id="2e20c-114">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2e20c-114">Click **OK** to close the dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="2e20c-115">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="2e20c-115">Next Step</span></span>  
 [<span data-ttu-id="2e20c-116">Tarea 8: Creación de una regla de dominio compuesto</span><span class="sxs-lookup"><span data-stu-id="2e20c-116">Task 8: Creating a Composite Domain Rule</span></span>](../../2014/tutorials/task-8-creating-a-composite-domain-rule.md)  
  
  
