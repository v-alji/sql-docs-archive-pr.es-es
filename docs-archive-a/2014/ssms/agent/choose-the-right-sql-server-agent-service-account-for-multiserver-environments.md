---
title: Elija la cuenta de servicio Agente SQL Server adecuada para entornos multiservidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, service accounts
- multiserver environments [SQL Server], SQL Server Agent service account behavior
ms.assetid: a07e2f38-281c-495b-965b-13fad03ba548
author: stevestein
ms.author: sstein
ms.openlocfilehash: 94ef890f5d2ef2b85d2f4d1023a93747e903a7f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677376"
---
# <a name="choose-the-right-sql-server-agent-service-account-for-multiserver-environments"></a><span data-ttu-id="449a3-102">Elegir la cuenta correcta del servicio del Agente SQL Server para entornos multiservidor</span><span class="sxs-lookup"><span data-stu-id="449a3-102">Choose the Right SQL Server Agent Service Account for Multiserver Environments</span></span>
  <span data-ttu-id="449a3-103">La cuenta de Windows que elija para el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede afectar al comportamiento de un entorno multiservidor, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="449a3-103">The Windows account you choose for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service can affect the behavior of a multiserver environment, as follows:</span></span>  
  
-   <span data-ttu-id="449a3-104">Si ejecuta el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en una cuenta que no sea miembro del grupo de administradores de Windows local, el alta de los servidores de destino en los servidores maestros puede generar un error.</span><span class="sxs-lookup"><span data-stu-id="449a3-104">If you run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service under an account that is not a member of the local Windows Administrators group, enlisting target servers to master servers may fail.</span></span> <span data-ttu-id="449a3-105">Si lo hace, se devuelve un mensaje de error que indica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="449a3-105">If it does, the following error message is returned:</span></span>  
  
     <span data-ttu-id="449a3-106">Error en la operación de alta.</span><span class="sxs-lookup"><span data-stu-id="449a3-106">"The enlistment operation failed."</span></span>  
  
     <span data-ttu-id="449a3-107">Reinicie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para solucionar este problema.</span><span class="sxs-lookup"><span data-stu-id="449a3-107">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services to resolve this issue.</span></span>  
  
-   <span data-ttu-id="449a3-108">Cuando el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se ejecuta en la cuenta del sistema local, las operaciones entre el servidor maestro y el servidor de destino solo se admiten si ambos servidores residen en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="449a3-108">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is run under the Local System account, master server-target server operations are supported only if both the master server and the target server reside on the same computer.</span></span> <span data-ttu-id="449a3-109">Si usa esta configuración, verá el siguiente mensaje cuando dé de alta los servidores de destino en un servidor maestro:</span><span class="sxs-lookup"><span data-stu-id="449a3-109">If you use this configuration, the following message is returned when you enlist target servers to a master server:</span></span>  
  
     <span data-ttu-id="449a3-110">"Comprobar que la cuenta de inicio del agente de *<nombre_equipo_servidor_destino>* posea derechos para iniciar la sesión como servidor de destino".</span><span class="sxs-lookup"><span data-stu-id="449a3-110">"Ensure the agent start-up account for *<target_server_computer_name>* has rights to log on as targetServer."</span></span>  
  
     <span data-ttu-id="449a3-111">Puede omitir este mensaje informativo.</span><span class="sxs-lookup"><span data-stu-id="449a3-111">You can ignore this informational message.</span></span> <span data-ttu-id="449a3-112">La operación de alta debe finalizar correctamente.</span><span class="sxs-lookup"><span data-stu-id="449a3-112">The enlistment operation should complete successfully.</span></span>  
  
 <span data-ttu-id="449a3-113">Para más información sobre cómo elegir una cuenta para el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte [Seleccionar una cuenta para el servicio del Agente SQL Server](select-an-account-for-the-sql-server-agent-service.md).</span><span class="sxs-lookup"><span data-stu-id="449a3-113">For more information about choosing an account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md).</span></span>  
  
  
