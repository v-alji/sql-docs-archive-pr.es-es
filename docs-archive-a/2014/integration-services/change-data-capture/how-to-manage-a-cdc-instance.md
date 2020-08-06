---
title: Cómo administrar una instancia CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5d9e677f-b872-497d-9cde-472184a214ab
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e387b9e1a75b7279a68d1c9c9b637f5473071013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744261"
---
# <a name="how-to-manage-a-cdc-instance"></a><span data-ttu-id="71a2d-102">How to Manage a CDC Instance</span><span class="sxs-lookup"><span data-stu-id="71a2d-102">How to Manage a CDC Instance</span></span>
  <span data-ttu-id="71a2d-103">En este procedimiento se describe cómo usar la Consola del diseñador CDC para administrar las operaciones de la instancia CDC en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="71a2d-103">This procedure describes how to use the CDC Designer Console to manage CDC instance operations at runtime.</span></span>  
  
### <a name="to-manage-cdc-instance-operations"></a><span data-ttu-id="71a2d-104">Para administrar las operaciones de la instancia CDC</span><span class="sxs-lookup"><span data-stu-id="71a2d-104">To manage CDC instance operations</span></span>  
  
1.  <span data-ttu-id="71a2d-105">En el menú **Inicio** , seleccione **Consola del diseñador CDC**.</span><span class="sxs-lookup"><span data-stu-id="71a2d-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="71a2d-106">En el panel izquierdo, expanda **Captura de datos modificados** y expanda después el servicio que contiene la instancia que desea ver.</span><span class="sxs-lookup"><span data-stu-id="71a2d-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance you want to view.</span></span>  
  
3.  <span data-ttu-id="71a2d-107">Seleccione el nombre de una instancia con la que desee trabajar.</span><span class="sxs-lookup"><span data-stu-id="71a2d-107">Select the name of an instance you want to work with.</span></span>  
  
4.  <span data-ttu-id="71a2d-108">En el panel **Acciones** situado en el lado derecho de la Consola del diseñador CDC, haga clic en la operación que desee realizar.</span><span class="sxs-lookup"><span data-stu-id="71a2d-108">From the **Actions** pane on the right side of the CDC Designer Console, click on the operation you want to carry out.</span></span>  
  
     <span data-ttu-id="71a2d-109">También puede hacer clic con el botón secundario en el nombre de la instancia en el panel izquierdo y seleccionar la operación que desee realizar.</span><span class="sxs-lookup"><span data-stu-id="71a2d-109">You can also right-click the name of the instance in the left pane and select the operation you want to carry out.</span></span>  
  
     <span data-ttu-id="71a2d-110">Puede realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="71a2d-110">You can carry out the following tasks:</span></span>  
  
    -   <span data-ttu-id="71a2d-111">**Iniciar**: para empezar a capturar cambios.</span><span class="sxs-lookup"><span data-stu-id="71a2d-111">**Start**: To start capturing changes.</span></span>  
  
    -   <span data-ttu-id="71a2d-112">**Detener**: para dejar de capturar cambios.</span><span class="sxs-lookup"><span data-stu-id="71a2d-112">**Stop**: To stop capturing changes</span></span>  
  
    -   <span data-ttu-id="71a2d-113">**Restablecer**: haga clic en **Restablecer** para restablecer la instancia CDC a su estado inicial (vacío).</span><span class="sxs-lookup"><span data-stu-id="71a2d-113">**Reset**: Click **Reset** to reset the CDC instance to its initial (empty) state.</span></span> <span data-ttu-id="71a2d-114">Esta opción está disponible cuando la instancia CDC está detenida.</span><span class="sxs-lookup"><span data-stu-id="71a2d-114">This option is available when the CDC instance is stopped.</span></span> <span data-ttu-id="71a2d-115">Se eliminan todos los cambios de las tablas de cambios y el estado interno de la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="71a2d-115">All changes in the change tables and the CDC instance internal state are deleted.</span></span> <span data-ttu-id="71a2d-116">Cuando se inicie la instancia CDC más adelante, la captura de cambios comenzará desde ese momento y solo incluirá las transacciones que comenzaron después de que se iniciara la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="71a2d-116">When the CDC instance is started later on, change capture will start from that point in time and only includes transactions that started after the CDC instance started.</span></span>  
  
    -   <span data-ttu-id="71a2d-117">**Eliminar**: para eliminar la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="71a2d-117">**Delete**: To delete the CDC instance.</span></span>  
  
    -   <span data-ttu-id="71a2d-118">**Script de registro de Oracle**: haga clic en **Oracle Logging Script** (Script de registro de Oracle) para mostrar el cuadro de diálogo Script de registro de Oracle con el script de registro complementario de Oracle.</span><span class="sxs-lookup"><span data-stu-id="71a2d-118">**Oracle Logging Script**: Click **Oracle Logging Script** to display the Oracle Logging script dialog box with the Oracle supplemental-logging script.</span></span> <span data-ttu-id="71a2d-119">Para obtener información acerca de lo que puede hacer en este cuadro de diálogo, vea [Oracle Supplemental Logging Script](oracle-supplemental-logging-script.md).</span><span class="sxs-lookup"><span data-stu-id="71a2d-119">For information on what you can do in this dialog box, see [Oracle Supplemental Logging Script](oracle-supplemental-logging-script.md).</span></span>  
  
         <span data-ttu-id="71a2d-120">**Nota**: al ejecutar los scripts de registro complementario, se abre el cuadro de diálogo Credenciales de Oracle para ejecutar script donde debe proporcionar un nombre de usuario y una contraseña válidos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="71a2d-120">**Note**: When you run the supplemental logging scripts, the Oracle Credentials for Running Script dialog box opens where you provide a valid Oracle user name and password.</span></span> <span data-ttu-id="71a2d-121">Para obtener información acerca de cómo proporcionar las credenciales adecuadas de Oracle, vea [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span><span class="sxs-lookup"><span data-stu-id="71a2d-121">For information on how to provide the proper Oracle credentials, see [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span></span>  
  
    -   <span data-ttu-id="71a2d-122">**Implementación de instancia CDC**: para generar un script de implementación para la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="71a2d-122">**CDC Instance Deployment**: To generate a deployment script for the CDC Instance.</span></span> <span data-ttu-id="71a2d-123">Para obtener información acerca de este cuadro de diálogo, vea [CDC Instance Deployment Script](cdc-instance-deployment-script.md).</span><span class="sxs-lookup"><span data-stu-id="71a2d-123">For information about this dialog box, see [CDC Instance Deployment Script](cdc-instance-deployment-script.md).</span></span>  
  
     <span data-ttu-id="71a2d-124">Para obtener más información acerca de estas tareas, vea [Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="71a2d-124">For more information about these tasks, see [Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
 <span data-ttu-id="71a2d-125">También puede seleccionar **Propiedades** para editar las propiedades de configuración de la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="71a2d-125">You can also select **Properties** to edit the CDC instance configuration properties.</span></span> <span data-ttu-id="71a2d-126">Para obtener más información acerca de cómo editar las propiedades de la instancia CDC, vea [Edit Instance Properties](edit-instance-properties.md).</span><span class="sxs-lookup"><span data-stu-id="71a2d-126">For more information about editing the CDC instance properties, see [Edit Instance Properties](edit-instance-properties.md).</span></span>  
  
  
