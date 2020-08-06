---
title: Elegir los servidores que configurar (Asistente para la configuración de seguridad de la creación de reflejo de bases de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.choosesrvrs.f1
ms.assetid: 59e23ff3-d7ee-4e32-9629-0b54d3a258f7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18e36f5c8ec020b3859dc847d1bbfc019817bcd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670576"
---
# <a name="choose-servers-to-configure-configure-database-mirroring-security-wizard"></a><span data-ttu-id="437fa-102">Elegir los servidores que configurar (Asistente para la configuración de seguridad de la creación de reflejo de bases de datos)</span><span class="sxs-lookup"><span data-stu-id="437fa-102">Choose Servers to Configure (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="437fa-103">Utilice esta página para especificar las instancias de servidor que desea configurar ahora.</span><span class="sxs-lookup"><span data-stu-id="437fa-103">Use this page to specify which server instances you want to configure now.</span></span> <span data-ttu-id="437fa-104">Debe seleccionar al menos una instancia de servidor antes de continuar con el asistente.</span><span class="sxs-lookup"><span data-stu-id="437fa-104">You must select at least one server instance before continuing the wizard.</span></span>  
  
 <span data-ttu-id="437fa-105">Si desactiva la casilla para una instancia de servidor, el asistente no realizará ningún cambio en ella.</span><span class="sxs-lookup"><span data-stu-id="437fa-105">If you clear the check box for a server instance, the wizard will not make any changes to it.</span></span> <span data-ttu-id="437fa-106">Sin embargo, el asistente le solicitará información acerca de esa instancia y guardará esta información como parte de la configuración de las otras instancias de servidor.</span><span class="sxs-lookup"><span data-stu-id="437fa-106">The wizard, however, will ask you to enter information about that instance and save this information as part of the configuration of the other server instances.</span></span> <span data-ttu-id="437fa-107">Por ejemplo, si desactiva la casilla de la instancia de servidor testigo, el asistente le solicitará la cuenta de servicio de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del testigo, ya que debe crearse un inicio de sesión para esa cuenta como parte de la configuración de seguridad que se guarda en las instancias del servidor principal y reflejado.</span><span class="sxs-lookup"><span data-stu-id="437fa-107">For example, if you clear the check box for the witness server instance, the wizard will ask you to enter the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account of the witness because a login for that account must be created as part of the security configuration saved at the principal and mirror server instances.</span></span>  
  
 <span data-ttu-id="437fa-108">**Para configurar la creación de reflejo de la base de datos mediante SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="437fa-108">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="437fa-109">Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="437fa-109">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="437fa-110">Iniciar el Asistente para la configuración de seguridad de la creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="437fa-110">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="437fa-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="437fa-111">Options</span></span>  
 <span data-ttu-id="437fa-112">**Instancia de servidor principal**</span><span class="sxs-lookup"><span data-stu-id="437fa-112">**Principal server instance**</span></span>  
 <span data-ttu-id="437fa-113">Seleccione esta opción para configurar la seguridad del servidor principal.</span><span class="sxs-lookup"><span data-stu-id="437fa-113">Select to configure security for the principal server.</span></span>  
  
 <span data-ttu-id="437fa-114">**Instancia del servidor reflejado**</span><span class="sxs-lookup"><span data-stu-id="437fa-114">**Mirror server instance**</span></span>  
 <span data-ttu-id="437fa-115">Seleccione esta opción para configurar la seguridad del servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="437fa-115">Select to configure security for the mirror server.</span></span>  
  
 <span data-ttu-id="437fa-116">**Instancia de servidor testigo**</span><span class="sxs-lookup"><span data-stu-id="437fa-116">**Witness server instance**</span></span>  
 <span data-ttu-id="437fa-117">Seleccione para configurar la seguridad del servidor testigo (si está presente).</span><span class="sxs-lookup"><span data-stu-id="437fa-117">Select to configure security for the witness server (if present).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="437fa-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="437fa-118">See Also</span></span>  
 <span data-ttu-id="437fa-119">[Propiedades de la base de datos &#40;página Creación de reflejo&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="437fa-119">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 [<span data-ttu-id="437fa-120">Creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="437fa-120">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
