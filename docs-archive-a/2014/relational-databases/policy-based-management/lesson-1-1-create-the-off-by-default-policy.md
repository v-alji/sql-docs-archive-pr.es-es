---
title: Creación de la directiva Desactivado de forma predeterminada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 98fde3c5-297c-4d95-981e-95700bbf5ccd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 16d0893c155627a41149263b5ce7b21a4a217b74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663434"
---
# <a name="create-the-off-by-default-policy"></a><span data-ttu-id="a892c-102">Crear la directiva Desactivado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="a892c-102">Create the Off By Default Policy</span></span>
  <span data-ttu-id="a892c-103">Esta tarea crea una condición denominada Correo desactivado que se basa en la faceta Configuración de área expuesta.</span><span class="sxs-lookup"><span data-stu-id="a892c-103">This task creates a condition named Mail Off that is based on the Surface Area Configuration facet.</span></span> <span data-ttu-id="a892c-104">A continuación, crea una directiva denominada Desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a892c-104">Then, it creates a policy named Off By Default.</span></span>  
  
### <a name="to-create-the-mail-off-condition"></a><span data-ttu-id="a892c-105">Para crear la condición Correo desactivado</span><span class="sxs-lookup"><span data-stu-id="a892c-105">To create the Mail Off condition</span></span>  
  
1.  <span data-ttu-id="a892c-106">En el Explorador de objetos, expanda **Administración**, **Administración de directivas**y **Facetas**, haga clic con el botón derecho en **Configuración de área expuesta**y, después, haga clic en **Nueva condición**.</span><span class="sxs-lookup"><span data-stu-id="a892c-106">In Object Explorer, expand **Management**, expand **Policy Management**, expand **Facets**, right-click **Surface Area Configuration**, and then click **New Condition**.</span></span>  
  
2.  <span data-ttu-id="a892c-107">En el cuadro de diálogo **Crear nueva condición** , en el cuadro **Nombre** , escriba **Correo desactivado**.</span><span class="sxs-lookup"><span data-stu-id="a892c-107">In the **Create New Condition** dialog box, in the **Name** box, type **Mail Off**.</span></span>  
  
3.  <span data-ttu-id="a892c-108">En el cuadro **Faceta** , confirme que está seleccionada la faceta **Configuración de área expuesta** .</span><span class="sxs-lookup"><span data-stu-id="a892c-108">In the **Facet** box, confirm that **Surface Area Configuration** facet is selected.</span></span>  
  
4.  <span data-ttu-id="a892c-109">En el área **Expresión**, en el cuadro **Campo**, seleccione **\@DatabaseMailEnabled**, en el cuadro **Operador**, seleccione **=** y, en **Valor**, seleccione **False**.</span><span class="sxs-lookup"><span data-stu-id="a892c-109">In the **Expression** area, in the **Field** box, select **\@DatabaseMailEnabled**, in the **Operator** box select **=**, and in the **Value** select **False**.</span></span>  
  
5.  <span data-ttu-id="a892c-110">En la página **Descripción** , escriba la descripción de la condición y luego haga clic en **Aceptar** para crear la condición.</span><span class="sxs-lookup"><span data-stu-id="a892c-110">On the **Description** page, type a description of the condition, and then click **OK** to create the condition.</span></span>  
  
### <a name="to-create-the-off-by-default-policy"></a><span data-ttu-id="a892c-111">Para crear la directiva Desactivado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="a892c-111">To create the Off By Default policy</span></span>  
  
1.  <span data-ttu-id="a892c-112">En el Explorador de objetos, haga clic con el botón derecho en **Configuración de área expuesta**y, después, haga clic en **Nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="a892c-112">In Object Explorer, right-click **Surface Area Configuration**, and then click **New Policy**.</span></span>  
  
2.  <span data-ttu-id="a892c-113">En el cuadro de diálogo **Crear nueva directiva** , en el cuadro **Nombre** , escriba **Desactivado de forma predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="a892c-113">In the **Create New Policy** dialog box, in the **Name** box, type **Off By Default**.</span></span>  
  
3.  <span data-ttu-id="a892c-114">Deje desactivada la casilla **Habilitado** .</span><span class="sxs-lookup"><span data-stu-id="a892c-114">Leave the **Enabled** checkbox unchecked.</span></span> <span data-ttu-id="a892c-115">La casilla **Habilitado** se aplica a las directivas automatizadas y esta directiva se ejecutará a petición.</span><span class="sxs-lookup"><span data-stu-id="a892c-115">The **Enabled** checkbox applies to automated policies, and this policy will be executed on demand.</span></span>  
  
4.  <span data-ttu-id="a892c-116">En la casilla **Condición de comprobación** , desplácese hacia abajo hasta el área **Configuración de área expuesta** y luego seleccione **Correo desactivado** como condición para comprobar.</span><span class="sxs-lookup"><span data-stu-id="a892c-116">In the **Check condition** checkbox, scroll down to the **Surface Area Configuration** area, and then select **Mail Off** as the condition to check.</span></span>  
  
5.  <span data-ttu-id="a892c-117">El cuadro **Para destinos** estará en blanco porque se trata de una directiva con ámbito de servidor.</span><span class="sxs-lookup"><span data-stu-id="a892c-117">The **Against targets** box will be blank because this is a server-scoped policy.</span></span>  
  
6.  <span data-ttu-id="a892c-118">En la casilla **Modo de evaluación** , seleccione **A petición** .</span><span class="sxs-lookup"><span data-stu-id="a892c-118">In the **Evaluation Mode** checkbox, select **On demand** as the evaluation mode.</span></span>  
  
7.  <span data-ttu-id="a892c-119">En la casilla **Restricción de servidor** , seleccione **Ninguna**.</span><span class="sxs-lookup"><span data-stu-id="a892c-119">In the **Server restriction** checkbox, select **None**.</span></span>  
  
8.  <span data-ttu-id="a892c-120">En la página **Descripción** , escriba la descripción de la directiva.</span><span class="sxs-lookup"><span data-stu-id="a892c-120">On the **Description** page, type a description of the policy.</span></span>  
  
9. <span data-ttu-id="a892c-121">Puede proporcionar un hipervínculo a una página web para las directivas en el área **Hipervínculo de ayuda adicional** .</span><span class="sxs-lookup"><span data-stu-id="a892c-121">You can provide a hyperlink to a Web page for your policies in the **Additional help hyperlink** area.</span></span> <span data-ttu-id="a892c-122">En el cuadro **Texto para mostrar** , escriba el texto que aparecerá para el hipervínculo.</span><span class="sxs-lookup"><span data-stu-id="a892c-122">In the **Text to display** box, type the text that will appear for the hyperlink.</span></span>  
  
10. <span data-ttu-id="a892c-123">En el cuadro **Dirección** , escriba un hipervínculo a una página de Ayuda, por ejemplo, la página principal del departamento de IT de la compañía.</span><span class="sxs-lookup"><span data-stu-id="a892c-123">In the **Address** box, type a hyperlink to a Help page, such as the home page for the IT department of your company.</span></span>  
  
11. <span data-ttu-id="a892c-124">Para confirmar la dirección y abrir la página web, haga clic en **Probar vínculo**.</span><span class="sxs-lookup"><span data-stu-id="a892c-124">To confirm the address by opening the Web page, click **Test Link**.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a892c-125">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="a892c-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a892c-126">Configurar un servidor para ejecutar la directiva Desactivado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="a892c-126">Configure a Server to Run the Off By Default Policy</span></span>](lesson-1-2-configure-a-server-to-run-the-off-by-default-policy.md)  
  
  
