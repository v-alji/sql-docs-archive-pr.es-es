---
title: Cuentas de servicio (Asistente para la configuración de seguridad de la creación de reflejo de bases de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.serviceaccounts.f1
ms.assetid: d58d8f93-7888-4d66-af4d-969ef6a2dbee
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 58e49467a28e816c6592b1ded212b5aea0e6bc55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746485"
---
# <a name="service-accounts-configure-database-mirroring-security-wizard"></a><span data-ttu-id="7fd51-102">Cuentas de servicio (Asistente para la configuración de seguridad de la creación de reflejo de bases de datos)</span><span class="sxs-lookup"><span data-stu-id="7fd51-102">Service Accounts (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="7fd51-103">Al utilizar la autenticación de Windows, si las instancias del servidor usan cuentas diferentes, especifique las cuentas de servicio para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fd51-103">When using Windows Authentication, if the server instances use different accounts, specify the service accounts for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7fd51-104">Estas cuentas de servicio deben ser cuentas de dominio (en el mismo dominio o en dominios de confianza).</span><span class="sxs-lookup"><span data-stu-id="7fd51-104">These service accounts must all be domain accounts (in the same or trusted domains).</span></span>  
  
 <span data-ttu-id="7fd51-105">Si todas las instancias del servidor utilizan la misma cuenta de dominio o la autenticación basada en certificados, deje los campos en blanco.</span><span class="sxs-lookup"><span data-stu-id="7fd51-105">If all the server instances use the same domain account or use certificate-based authentication, leave the fields blank.</span></span> <span data-ttu-id="7fd51-106">Basta con hacer clic en **Finalizar**y el asistente configura automáticamente las cuentas en función de la cuenta del asistente actual.</span><span class="sxs-lookup"><span data-stu-id="7fd51-106">Simply click **Finish**, and the wizard automatically configures the accounts based on the account of the current wizard.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7fd51-107">Si los extremos de creación de reflejo de la base de datos de las instancias de servidor están configurados para usar certificados, debe dejar vacíos los campos de cuenta de servicio.</span><span class="sxs-lookup"><span data-stu-id="7fd51-107">If the database mirroring endpoints of the server instances are configured to use certificates, you must leave the service account fields empty.</span></span>  
  
 <span data-ttu-id="7fd51-108">**Para configurar la creación de reflejo de la base de datos mediante SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="7fd51-108">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="7fd51-109">Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="7fd51-109">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="7fd51-110">Iniciar el Asistente para la configuración de seguridad de la creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="7fd51-110">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="7fd51-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="7fd51-111">Options</span></span>  
 <span data-ttu-id="7fd51-112">**Principal**</span><span class="sxs-lookup"><span data-stu-id="7fd51-112">**Principal**</span></span>  
 <span data-ttu-id="7fd51-113">Especifique la cuenta de servicio de la instancia de servidor principal.</span><span class="sxs-lookup"><span data-stu-id="7fd51-113">Specify the service account of the principal server instance.</span></span> <span data-ttu-id="7fd51-114">Escriba el nombre del dominio en mayúsculas:</span><span class="sxs-lookup"><span data-stu-id="7fd51-114">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="7fd51-115">*Dominio* \\ de *nombre de usuario*</span><span class="sxs-lookup"><span data-stu-id="7fd51-115">*DOMAINNAME*\\*username*</span></span>  
  
 <span data-ttu-id="7fd51-116">**Reflejo**</span><span class="sxs-lookup"><span data-stu-id="7fd51-116">**Mirror**</span></span>  
 <span data-ttu-id="7fd51-117">Especifique la cuenta de servicio de la instancia del servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="7fd51-117">Specify the service account of the mirror server instance.</span></span> <span data-ttu-id="7fd51-118">Escriba el nombre del dominio en mayúsculas:</span><span class="sxs-lookup"><span data-stu-id="7fd51-118">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="7fd51-119">*Dominio* \\ de *nombre de usuario*</span><span class="sxs-lookup"><span data-stu-id="7fd51-119">*DOMAINNAME*\\*username*</span></span>  
  
 <span data-ttu-id="7fd51-120">**Testigo**</span><span class="sxs-lookup"><span data-stu-id="7fd51-120">**Witness**</span></span>  
 <span data-ttu-id="7fd51-121">Especifique la cuenta de servicio de la instancia de servidor testigo.</span><span class="sxs-lookup"><span data-stu-id="7fd51-121">Specify the service account of the witness server instance.</span></span> <span data-ttu-id="7fd51-122">Escriba el nombre del dominio en mayúsculas:</span><span class="sxs-lookup"><span data-stu-id="7fd51-122">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="7fd51-123">*Dominio* \\ de *nombre de usuario*</span><span class="sxs-lookup"><span data-stu-id="7fd51-123">*DOMAINNAME*\\*username*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd51-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7fd51-124">See Also</span></span>  
 <span data-ttu-id="7fd51-125">[Propiedades de la base de datos &#40;página Creación de reflejo&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="7fd51-125">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="7fd51-126">[Iniciar el Monitor de creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="7fd51-126">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="7fd51-127">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7fd51-127">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="7fd51-128">Configurar cuentas de inicio de sesión para la creación de reflejo de la base de datos o Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7fd51-128">Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](set-up-login-accounts-database-mirroring-always-on-availability.md)  
  
  
