---
title: Complete los pasos posteriores a la instalación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 0a788a2a-9b4f-4bfc-b1b5-83eeb1ea9ab2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1e9aae3dccaa409bcebc473213286f3edf19e7f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673951"
---
# <a name="complete-the-post-installation-steps"></a><span data-ttu-id="98ecc-102">Completar los pasos posteriores a la instalación</span><span class="sxs-lookup"><span data-stu-id="98ecc-102">Complete the Post-Installation Steps</span></span>
  <span data-ttu-id="98ecc-103">Después de instalar Distributed Replay debe modificar las cuentas de los servicios de controlador y de cliente de Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="98ecc-103">After you install Distributed Replay you must modify the Distributed Replay controller and client services accounts.</span></span>  
  
### <a name="to-complete-the-post-installation-steps"></a><span data-ttu-id="98ecc-104">Para completar los pasos posteriores a la instalación</span><span class="sxs-lookup"><span data-stu-id="98ecc-104">To complete the post-installation steps</span></span>  
  
1.  <span data-ttu-id="98ecc-105">**Cree reglas de firewall**: en los equipos del controlador y cliente, debe permitir el tráfico entrante a través del firewall para el servicio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="98ecc-105">**Create firewall rules**: On the controller and client computers, you must allow inbound traffic through the firewall for the corresponding service.</span></span> <span data-ttu-id="98ecc-106">Especifique las reglas de firewall para los ejecutables del servicio, ubicados en las carpetas de instalación.</span><span class="sxs-lookup"><span data-stu-id="98ecc-106">Specify the firewall rules for the service executables, located in the installation folders.</span></span>  
  
    1.  <span data-ttu-id="98ecc-107">Para el servicio del controlador, cree una regla para **DReplayController.exe**, ubicada en la carpeta de instalación.</span><span class="sxs-lookup"><span data-stu-id="98ecc-107">For the controller service, create a rule for **DReplayController.exe**, located in the installation folder.</span></span> <span data-ttu-id="98ecc-108">Por ejemplo, el comando siguiente habilita esta regla, donde `%InstallPath%` es la carpeta de instalación del servicio:</span><span class="sxs-lookup"><span data-stu-id="98ecc-108">For example, the following command enables this rule, where `%InstallPath%` is the installation folder of the service:</span></span>  
  
         `netsh advfirewall firewall add rule name="allow dreplay controller" dir=in program="%InstallPath%\DReplayController\DReplayController.exe" action=allow`  
  
    2.  <span data-ttu-id="98ecc-109">Para el servicio de cliente, en cada equipo cliente, cree una regla para **DReplayClient.exe**, ubicada en la carpeta de instalación.</span><span class="sxs-lookup"><span data-stu-id="98ecc-109">For the client service, on each client computer, create a rule for **DReplayClient.exe**, located in the installation folder.</span></span> <span data-ttu-id="98ecc-110">Por ejemplo, el comando siguiente habilita esta regla, donde `%InstallPath%` es la carpeta de instalación del servicio:</span><span class="sxs-lookup"><span data-stu-id="98ecc-110">For example, the following command enables this rule, where `%InstallPath%` is the installation folder of the service:</span></span>  
  
         `netsh advfirewall firewall add rule name="allow dreplay client" dir=in program="%InstallPath%\DReplayClient\DReplayClient.exe" action=allow`  
  
2.  <span data-ttu-id="98ecc-111">**Conceda permisos a todos los clientes en el servidor de destino**: después de completar la instalación del servicio de cliente en los equipos cliente, debe agregar manualmente las cuentas del servicio de cliente al rol sysadmin en la instancia de destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98ecc-111">**Grant each client permissions on the target server**: After you have completed installing the client service on the client computers, you must manually add the client service accounts to the sysadmin role on the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="98ecc-112">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="98ecc-112">.NET Framework Security</span></span>  
 <span data-ttu-id="98ecc-113">Debe disponer de permisos administrativos para instalar cualquiera de las características de Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="98ecc-113">You must have administrative permissions in order to install any of the Distributed Replay features.</span></span> <span data-ttu-id="98ecc-114">Solo un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con permisos sysadmin puede agregar las cuentas del servicio de cliente al rol de servidor sysadmin del servidor de prueba.</span><span class="sxs-lookup"><span data-stu-id="98ecc-114">Only a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login having sysadmin permissions can add the client service accounts to the sysadmin server role of the test server.</span></span> <span data-ttu-id="98ecc-115">Para obtener más información sobre las consideraciones de seguridad de Distributed Replay, vea [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="98ecc-115">For more information about Distributed Replay security considerations, see [Distributed Replay Security](distributed-replay-security.md).</span></span>  
  
  
