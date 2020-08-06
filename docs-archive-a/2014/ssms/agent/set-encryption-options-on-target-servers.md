---
title: Establecer opciones de cifrado en servidores de destino | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, encryption
- target servers [SQL Server], encryption
- multiserver environments [SQL Server], setting encryption options on target servers
ms.assetid: 1a9fd539-e166-4ea8-9f21-ac400ca74dee
author: stevestein
ms.author: sstein
ms.openlocfilehash: cd10d2e05e59015542f41cc123de993e6128f9f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676314"
---
# <a name="set-encryption-options-on-target-servers"></a><span data-ttu-id="ad0e8-102">Establecer opciones de cifrado en servidores de destino</span><span class="sxs-lookup"><span data-stu-id="ad0e8-102">Set Encryption Options on Target Servers</span></span>
  <span data-ttu-id="ad0e8-103">Si no puede usar un certificado para comunicaciones cifradas con Capa de sockets seguros (SSL) entre servidores principales y alguno o todos los servidores de destino, pero desea cifrar el canal entre ellos, configure el servidor de destino para usar el nivel de seguridad necesario.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-103">If you cannot use a certificate for Secure Sockets Layer (SSL) encrypted communications between master servers and some or all of your target servers, but you want to encrypt the channel between them, configure the target server to use the level of security required.</span></span>  
  
 <span data-ttu-id="ad0e8-104">Para configurar el nivel de seguridad adecuado necesario para un canal de comunicación específico entre un servidor maestro y un servidor de destino, establezca la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] subclave del registro del agente **\ HKEY_LOCAL_MACHINE \software\microsoft\microsoft \\ SQL Server** \<*instance_name*> **\SQLServerAgent\MsxEncryptChannelOptions (REG_DWORD)** en el servidor de destino en uno de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-104">To configure the appropriate level of security required for a specific master server/target server communication channel, set the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\**\<*instance_name*>**\SQLServerAgent\MsxEncryptChannelOptions(REG_DWORD)** on the target server to one of the following values.</span></span> <span data-ttu-id="ad0e8-105">El valor de \<*instance_name*> es **MSSQL.** _n_.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-105">The value of \<*instance_name*> is **MSSQL.**_n_.</span></span> <span data-ttu-id="ad0e8-106">Por ejemplo, **MSSQL.1** o **MSSQL.3**.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-106">For example, **MSSQL.1** or **MSSQL.3**.</span></span>  
  
|<span data-ttu-id="ad0e8-107">Value</span><span class="sxs-lookup"><span data-stu-id="ad0e8-107">Value</span></span>|<span data-ttu-id="ad0e8-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad0e8-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ad0e8-109">**0**</span><span class="sxs-lookup"><span data-stu-id="ad0e8-109">**0**</span></span>|<span data-ttu-id="ad0e8-110">Deshabilita el cifrado entre este servidor de destino y el servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-110">Disables encryption between this target server and the master server.</span></span> <span data-ttu-id="ad0e8-111">Elija esta opción únicamente cuando el canal entre el servidor de destino y el servidor principal se ha protegido por otros medios.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-111">Choose this option only when the channel between the target server and master server is secured by another means.</span></span>|  
|<span data-ttu-id="ad0e8-112">**1**</span><span class="sxs-lookup"><span data-stu-id="ad0e8-112">**1**</span></span>|<span data-ttu-id="ad0e8-113">Habilita el cifrado solo entre este servidor de destino y el servidor principal, pero no se requiere validación de certificados.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-113">Enables encryption only between this target server and the master server, but no certificate validation is required.</span></span>|  
|<span data-ttu-id="ad0e8-114">**2**</span><span class="sxs-lookup"><span data-stu-id="ad0e8-114">**2**</span></span>|<span data-ttu-id="ad0e8-115">Habilita el cifrado SSL y la validación de certificados completos entre este servidor de destino y el servidor principal.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-115">Enables full SSL encryption and certificate validation between this target server and the master server.</span></span> <span data-ttu-id="ad0e8-116">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-116">This setting is the default.</span></span> <span data-ttu-id="ad0e8-117">A menos que tenga una razón concreta para elegir un valor diferente, se recomienda no modificarlo.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-117">Unless you have specific reason to choose a different value, we recommend not changing it.</span></span>|  
  
 <span data-ttu-id="ad0e8-118">Si se especifica **1** o **2** , debe tener habilitado SSL en los servidores maestro y de destino.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-118">If **1** or **2** is specified, you must have SSL enabled on both the master and target servers.</span></span> <span data-ttu-id="ad0e8-119">Si se especifica **2** , debe tener además un certificado debidamente firmado presente en el servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="ad0e8-119">If **2** is specified, you must also have a properly signed certificate present on the master server.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ad0e8-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad0e8-120">See Also</span></span>  
 [<span data-ttu-id="ad0e8-121">Habilitar conexiones cifradas en el motor de base de datos &#40;Administrador de configuración de SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ad0e8-121">Enable Encrypted Connections to the Database Engine &#40;SQL Server Configuration Manager&#41;</span></span>](../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md)  
  
  
