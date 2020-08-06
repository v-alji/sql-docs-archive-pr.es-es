---
title: 'Tarea 4: establecer reglas de dominio | Microsoft Docs'
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3a7162ba-cf2f-481f-830d-bb6a02823827
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42bdbd0228fdd3515f68ce830581f445242768e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663205"
---
# <a name="task-4-setting-domain-rules"></a><span data-ttu-id="4351b-102">Tarea 4: Configuración de reglas de dominio</span><span class="sxs-lookup"><span data-stu-id="4351b-102">Task 4: Setting Domain Rules</span></span>
  <span data-ttu-id="4351b-103">En esta tarea, creará una regla para el dominio de **correo electrónico de contacto** para comprobar si la dirección de correo electrónico finaliza con \*\* \@ Adventure-Works.com\*\*.</span><span class="sxs-lookup"><span data-stu-id="4351b-103">In this task, you create a rule for the **Contact Email** domain to verify if the email address ends with **\@adventure-works.com**.</span></span> <span data-ttu-id="4351b-104">Vea el tema [Crear una regla de dominio](https://msdn.microsoft.com/library/hh510397.aspx) para obtener más detalles sobre la página.</span><span class="sxs-lookup"><span data-stu-id="4351b-104">See [Creating a Domain Rule](https://msdn.microsoft.com/library/hh510397.aspx) topic for more details on the page.</span></span>  
  
1.  <span data-ttu-id="4351b-105">Haga clic en **Correo electrónico de contacto** en la lista **Dominio**.</span><span class="sxs-lookup"><span data-stu-id="4351b-105">Click **Contact Email** in the **Domain list**.</span></span>  
  
2.  <span data-ttu-id="4351b-106">Cambie a la pestaña **Reglas de dominio** en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="4351b-106">Switch to the **Domain Rules** tab in the right pane.</span></span>  
  
     <span data-ttu-id="4351b-107">![Botón de la barra de herramientas Agregar una nueva regla de dominio](../../2014/tutorials/media/et-settingdomainrules-01.jpg "Botón de la barra de herramientas Agregar una nueva regla de dominio")</span><span class="sxs-lookup"><span data-stu-id="4351b-107">![Add a New Domain Rule Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-01.jpg "Add a New Domain Rule Toolbar Button")</span></span>  
  
3.  <span data-ttu-id="4351b-108">En el panel derecho, haga clic en el botón **Agregar una nueva regla de dominio** de la barra de herramientas (vea la imagen) para agregar una regla.</span><span class="sxs-lookup"><span data-stu-id="4351b-108">In the right pane, click **Add a new domain rule** button on the toolbar (see the image) to add a rule.</span></span>  
  
4.  <span data-ttu-id="4351b-109">Escriba **Validación de correo electrónico** como **Nombre de regla** y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="4351b-109">Type **Email Validation** for the **rule name** and press **ENTER**.</span></span> <span data-ttu-id="4351b-110">La casilla **Activa** debe estar activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4351b-110">The **Active** check box should be checked by default.</span></span> <span data-ttu-id="4351b-111">Este control le permite desactivar una regla temporalmente.</span><span class="sxs-lookup"><span data-stu-id="4351b-111">This control allows you to deactivate a rule temporarily.</span></span>  
  
5.  <span data-ttu-id="4351b-112">En el panel **Generar una regla** , haga clic en la **flecha abajo**y seleccione **El valor termina por**.</span><span class="sxs-lookup"><span data-stu-id="4351b-112">In the **Build a Rule** pane, click **down arrow**, and select **Value ends with**.</span></span>  
  
6.  <span data-ttu-id="4351b-113">Escriba \*\* \@ Adventure-Works.com\*\* en el cuadro de texto y presione **Tab**.</span><span class="sxs-lookup"><span data-stu-id="4351b-113">Type **\@adventure-works.com** in the text box and press **TAB**.</span></span> <span data-ttu-id="4351b-114">Puede agregar más condiciones si hace clic en el botón **Agregar una nueva condición a la cláusula seleccionada** de la barra de herramientas del panel **Generar una regla** .</span><span class="sxs-lookup"><span data-stu-id="4351b-114">You can add more conditions by clicking **Add a new condition to the selected clause** toolbar button in the **Build a Rule** pane.</span></span>  
  
     <span data-ttu-id="4351b-115">![Regla de validación de correo electrónico](../../2014/tutorials/media/et-settingdomainrules-02.jpg "Regla de validación de correo electrónico")</span><span class="sxs-lookup"><span data-stu-id="4351b-115">![Email Validation Rule](../../2014/tutorials/media/et-settingdomainrules-02.jpg "Email Validation Rule")</span></span>  
  
7.  <span data-ttu-id="4351b-116">Haga clic en el botón **Ejecutar la regla de dominio seleccionada en los datos de prueba** de la barra de herramientas del panel derecho para probar la regla con datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4351b-116">Click **Run the selected domain rule on test data** button on the toolbar in the right pane to test the rule against sample data.</span></span>  
  
     <span data-ttu-id="4351b-117">![Botón de la barra de herramientas Ejecutar la regla de dominio seleccionada en los datos de prueba](../../2014/tutorials/media/et-settingdomainrules-03.jpg "Botón de la barra de herramientas Ejecutar la regla de dominio seleccionada en los datos de prueba")</span><span class="sxs-lookup"><span data-stu-id="4351b-117">![Run the Domain Rule on Test Data Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-03.jpg "Run the Domain Rule on Test Data Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="4351b-118">En el cuadro de diálogo **Probar regla de dominio** , haga clic en el botón **Agrega un nuevo término de prueba para la regla de dominio** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="4351b-118">In the **Test Domain Rule** dialog box, click **Adds a new testing term for the domain rule** button on the toolbar.</span></span>  
  
     <span data-ttu-id="4351b-119">![Cuadro de diálogo Probar regla de dominio](../../2014/tutorials/media/et-settingdomainrules-04.jpg "Cuadro de diálogo Probar regla de dominio")</span><span class="sxs-lookup"><span data-stu-id="4351b-119">![Test Domain Rule Dialog Box](../../2014/tutorials/media/et-settingdomainrules-04.jpg "Test Domain Rule Dialog Box")</span></span>  
  
9. <span data-ttu-id="4351b-120">Escriba **frank7 \@ Adventure-Works.com** (un valor válido) en la columna **correo electrónico de contacto** .</span><span class="sxs-lookup"><span data-stu-id="4351b-120">Type **frank7\@adventure-works.com** (a valid value) in the **Contact Email** column.</span></span>  
  
10. <span data-ttu-id="4351b-121">Repita los dos pasos anteriores para agregar **joe2 \@ Adventure-work.com** (un valor no válido sin ') '.</span><span class="sxs-lookup"><span data-stu-id="4351b-121">Repeat previous two steps to add **joe2\@adventure-work.com** (an invalid value with no 's').</span></span>  
  
11. <span data-ttu-id="4351b-122">Haga clic en el último botón (**Probar la regla de dominio en todos los términos**) de la barra de herramientas para probar los datos de entrada con la regla.</span><span class="sxs-lookup"><span data-stu-id="4351b-122">Click the last button (**Test the domain rule on all the terms**) on the toolbar to test the input data against the rule.</span></span>  
  
     <span data-ttu-id="4351b-123">![Botón de la barra de herramientas Probar la regla de dominio en todos los términos](../../2014/tutorials/media/et-settingdomainrules-05.jpg "Botón de la barra de herramientas Probar la regla de dominio en todos los términos")</span><span class="sxs-lookup"><span data-stu-id="4351b-123">![Test the Domain Rule on All Terms Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-05.jpg "Test the Domain Rule on All Terms Toolbar Button")</span></span>  
  
12. <span data-ttu-id="4351b-124">Observe que la primera entrada se muestra como un elemento válido y el segundo como un elemento no válido.</span><span class="sxs-lookup"><span data-stu-id="4351b-124">Notice that the first entry is shown as a valid item and the second one as an invalid item.</span></span>  
  
     <span data-ttu-id="4351b-125">![Resultados de la prueba de la regla de dominio](../../2014/tutorials/media/et-settingdomainrules-06.jpg "Resultados de la prueba de la regla de dominio")</span><span class="sxs-lookup"><span data-stu-id="4351b-125">![Test Domain Rule Results](../../2014/tutorials/media/et-settingdomainrules-06.jpg "Test Domain Rule Results")</span></span>  
  
13. <span data-ttu-id="4351b-126">Haga clic en **Cerrar** para cerrar el cuadro de diálogo **Probar regla de dominio** .</span><span class="sxs-lookup"><span data-stu-id="4351b-126">Click **Close** to close the **Test Domain Rule** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="4351b-127">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="4351b-127">Next Step</span></span>  
 [<span data-ttu-id="4351b-128">Tarea 5: Configuración de relaciones basadas en términos</span><span class="sxs-lookup"><span data-stu-id="4351b-128">Task 5: Setting Term Based Relationships</span></span>](../../2014/tutorials/task-5-setting-term-based-relationships.md)  
  
  
