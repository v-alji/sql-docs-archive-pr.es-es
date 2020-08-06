---
title: Change Data Capture Service para Oracle de Attunity | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 22ec8a5c-9550-4d38-8a4a-485ec3e53ea8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68e68e9edd91bd1d0c718b32e29c3b29f74778c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673856"
---
# <a name="change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="b74ba-102">Servicio de captura de datos modificados para Oracle de Attunity</span><span class="sxs-lookup"><span data-stu-id="b74ba-102">Change Data Capture Service for Oracle by Attunity</span></span>
  <span data-ttu-id="b74ba-103">El servicio CDC para Oracle es un servicio de Windows que examina los registros de transacciones de Oracle y captura los cambios a las tablas de Oracle deseadas en tablas de cambios de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b74ba-103">The CDC Service for Oracle is a Windows service that scans Oracle transaction logs and captures changes to Oracle tables of interest into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] change tables.</span></span> <span data-ttu-id="b74ba-104">Las tablas de cambios de SQL donde se almacenan los cambios capturados de Oracle son el mismo tipo de tablas de cambios empleadas en la característica de captura de datos modificados nativa de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b74ba-104">The SQL change tables where the changes captured from Oracle are stored are the same type of change tables used in the native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Change Data Capture feature.</span></span> <span data-ttu-id="b74ba-105">Esto hace que el uso de estos cambios sea tan sencillo como el de los cambios realizados a las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b74ba-105">This makes consuming these changes as easy as consuming changes made to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="b74ba-106">Instalación</span><span class="sxs-lookup"><span data-stu-id="b74ba-106">Installation</span></span>  
 <span data-ttu-id="b74ba-107">El servicio CDC para Oracle se puede instalar en cualquier equipo compatible con Windows que tenga acceso a las bases de datos de origen de Oracle que se van a capturar y a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino donde reside la base de datos CDC de destino.</span><span class="sxs-lookup"><span data-stu-id="b74ba-107">The CDC Service for Oracle can be installed on any supported Windows computer with access to the source Oracle database(s) being captured and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance where the target CDC database resides.</span></span> <span data-ttu-id="b74ba-108">El servicio CDC no necesita ninguna instalación local de la base de datos de Oracle ni de la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , solo sus clientes compatibles.</span><span class="sxs-lookup"><span data-stu-id="b74ba-108">The CDC Service does not need a local installation of the Oracle database or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, only their supported clients.</span></span> <span data-ttu-id="b74ba-109">Para obtener información acerca de dónde instalar los componentes de base de datos necesarios, vea **Requisitos previos de la base de datos** en este tema.</span><span class="sxs-lookup"><span data-stu-id="b74ba-109">For information about where to install the required database components, see **Database Prerequisites** in this topic.</span></span>  
  
 <span data-ttu-id="b74ba-110">La instalación del servicio CDC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para Oracle coloca la interfaz de usuario de configuración del servicio y el programa de servicio en la ubicación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b74ba-110">The installation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC Service for Oracle places the service configuration UI and the service program in the selected location.</span></span> <span data-ttu-id="b74ba-111">El servicio CDC para Oracle se configura de forma independiente mediante la Consola de configuración del servicio CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="b74ba-111">The CDC Service for Oracle is configured separately using the Oracle CDC Service Configuration Console.</span></span> <span data-ttu-id="b74ba-112">Para obtener más información acerca de cómo configurar el servicio CDC de Oracle, vea [Servicio de captura de datos modificados para Oracle de Attunity (Ayuda de F1)](change-data-capture-service-for-oracle-by-attunity-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="b74ba-112">For more information on configuring the Oracle CDC Service, see [Change Data Capture Service for Oracle by Attunity F1 Help](change-data-capture-service-for-oracle-by-attunity-f1-help.md).</span></span>  
  
 <span data-ttu-id="b74ba-113">Para instalar el servicio CDC para Oracle, ejecute manualmente **AttunityOracleCdcService.msi** desde los medios de instalación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b74ba-113">To install the CDC Service for Oracle, manually run **AttunityOracleCdcService.msi** from the SQL Server installation media.</span></span> <span data-ttu-id="b74ba-114">Los paquetes de instalación para x86 y x64 se encuentran en \*\*.\Tools\AttunityCDCOracle \\ \*\* en los medios de instalación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b74ba-114">Installation packages for x86 and x64 are located in **.\Tools\AttunityCDCOracle\\** on the SQL Server installation media.</span></span>  
  
 <span data-ttu-id="b74ba-115">El servicio CDC para Oracle se puede instalar en cualquier equipo compatible con Windows donde esté instalado [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client; no es necesario instalarlo en el mismo equipo donde está instalado [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="b74ba-115">The CDC Service for Oracle can be installed on any supported Windows computer where the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client is installed; it does not need to be installed on the same computer where the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
## <a name="supported-windows-environments"></a><span data-ttu-id="b74ba-116">Entornos de Windows admitidos</span><span class="sxs-lookup"><span data-stu-id="b74ba-116">Supported Windows Environments</span></span>  
 <span data-ttu-id="b74ba-117">El Servicio de captura de datos modificados para Oracle de Attunity se puede ejecutar en los entornos de Windows siguientes:</span><span class="sxs-lookup"><span data-stu-id="b74ba-117">The Change Data Capture Service for Oracle by Attunity can run in the following Windows environments:</span></span>  
  
-   <span data-ttu-id="b74ba-118">Windows 8</span><span class="sxs-lookup"><span data-stu-id="b74ba-118">Windows 8</span></span>  
  
-   <span data-ttu-id="b74ba-119">Windows 7 de 32 bits (x86) y 64 bits (x64)</span><span class="sxs-lookup"><span data-stu-id="b74ba-119">Windows 7 32-bit (x86) and 64-bit (x64)</span></span>  
  
-   <span data-ttu-id="b74ba-120">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b74ba-120">Windows Server 2012</span></span>  
  
-   <span data-ttu-id="b74ba-121">Windows Server 2008 R2 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="b74ba-121">Windows Server 2008 R2 with Service Pack 1</span></span>  
  
-   <span data-ttu-id="b74ba-122">Windows Server 2008 de 32 bits (x86) y 64 bits (x64) con Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="b74ba-122">Windows Server 2008 32-bit (x86) and 64-bit (x64) with Service Pack 2</span></span>  
  
## <a name="database-prerequisites"></a><span data-ttu-id="b74ba-123">Requisitos previos de la base de datos</span><span class="sxs-lookup"><span data-stu-id="b74ba-123">Database Prerequisites</span></span>  
 <span data-ttu-id="b74ba-124">Para trabajar con el servicio CDC para Oracle debe instalar el software de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client Oracle.</span><span class="sxs-lookup"><span data-stu-id="b74ba-124">To work with the CDC Service for Oracle you must install the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client Oracle software.</span></span> <span data-ttu-id="b74ba-125">Se trata de un requisito previo que se debe obtener de Oracle e instalar antes de instalar el servicio CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="b74ba-125">This is a prerequisite that should be obtained from Oracle and installed before installing the Oracle CDC Service.</span></span> <span data-ttu-id="b74ba-126">Además, debe instalar el cliente ODBC de SQL Server mediante el programa de instalación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b74ba-126">Additionally, you need to install the SQL Server ODBC Client using SQL Server Setup.</span></span>  
  
 <span data-ttu-id="b74ba-127">El servicio CDC para Oracle admite las versiones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b74ba-127">The CDC Service for Oracle supports the following versions:</span></span>  
  
### <a name="source-oracle-database"></a><span data-ttu-id="b74ba-128">Base de datos de Oracle de origen</span><span class="sxs-lookup"><span data-stu-id="b74ba-128">Source Oracle Database</span></span>  
  
-   <span data-ttu-id="b74ba-129">Oracle Database 11x, cualquier versión</span><span class="sxs-lookup"><span data-stu-id="b74ba-129">Oracle Database 11x, any version</span></span>  
  
-   <span data-ttu-id="b74ba-130">Oracle Database 10x, cualquier versión</span><span class="sxs-lookup"><span data-stu-id="b74ba-130">Oracle Database 10x, any version</span></span>  
  
### <a name="target-sql-server-database"></a><span data-ttu-id="b74ba-131">Base de datos de SQL Server de destino</span><span class="sxs-lookup"><span data-stu-id="b74ba-131">Target SQL Server Database</span></span>  
 <span data-ttu-id="b74ba-132">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="b74ba-132">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="running-the-installation-program"></a><span data-ttu-id="b74ba-133">Ejecutar el programa de instalación</span><span class="sxs-lookup"><span data-stu-id="b74ba-133">Running the Installation Program</span></span>  
 <span data-ttu-id="b74ba-134">Para instalar el servicio CDC para Oracle, abra el asistente para la instalación para la plataforma Windows que esté usando (32 o 64 bits) y siga las instrucciones de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="b74ba-134">To install the CDC Service for Oracle, open the installation wizard for the Windows platform you are using (32/64-bit) and follow the directions on the screen.</span></span>  
  
## <a name="uninstalling-change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="b74ba-135">Desinstalar el servicio de captura de datos modificados para Oracle de Attunity</span><span class="sxs-lookup"><span data-stu-id="b74ba-135">Uninstalling Change Data Capture Service for Oracle by Attunity</span></span>  
 <span data-ttu-id="b74ba-136">La desinstalación del servicio CDC para Oracle se realiza mediante Panel de control, Programas y características.</span><span class="sxs-lookup"><span data-stu-id="b74ba-136">You uninstall the CDC Service for Oracle using Control Panel, Programs and Features.</span></span>  
  
 <span data-ttu-id="b74ba-137">Al desinstalar el servicio CDC no se eliminan las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creadas.</span><span class="sxs-lookup"><span data-stu-id="b74ba-137">Uninstalling the CDC Service does not delete the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases created.</span></span> <span data-ttu-id="b74ba-138">Para quitar completamente la herramienta, debe quitar la base de datos MSXDBCDC y las bases de datos CDC específicas que se crearon en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino con la que trabajó.</span><span class="sxs-lookup"><span data-stu-id="b74ba-138">For complete removal of the tool, you must remove the MSXDBCDC database and the specific CDC databases that were created in the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you worked with.</span></span>  
  
 <span data-ttu-id="b74ba-139">Si desinstala el software del servicio CDC de un equipo y lo instala en otro equipo, solo tiene que proporcionar las definiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b74ba-139">If you uninstall the CDC Service software from one machine and install it on another computer, you only need to provide the following definitions:</span></span>  
  
-   <span data-ttu-id="b74ba-140">Cuenta de servicio</span><span class="sxs-lookup"><span data-stu-id="b74ba-140">Service account</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b74ba-141">Cadena de conexión y credenciales</span><span class="sxs-lookup"><span data-stu-id="b74ba-141">connect string and credentials</span></span>  
  
-   <span data-ttu-id="b74ba-142">La contraseña maestra</span><span class="sxs-lookup"><span data-stu-id="b74ba-142">The master password</span></span>  
  
 <span data-ttu-id="b74ba-143">Todas las demás definiciones están almacenadas en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y están disponibles de la instalación anterior en el otro equipo.</span><span class="sxs-lookup"><span data-stu-id="b74ba-143">All the other definitions are stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and are available from the previous installation on another computer.</span></span>  
  
## <a name="in-this-documentation"></a><span data-ttu-id="b74ba-144">En esta documentación</span><span class="sxs-lookup"><span data-stu-id="b74ba-144">In This Documentation</span></span>  
  
-   [<span data-ttu-id="b74ba-145">Servicio de captura de datos modificados para Oracle de Attunity (Arquitectura del sistema)</span><span class="sxs-lookup"><span data-stu-id="b74ba-145">Change Data Capture Service for Oracle by Attunity System Architecture</span></span>](change-data-capture-service-for-oracle-by-attunity-system-architecture.md)  
  
-   [<span data-ttu-id="b74ba-146">El servicio CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="b74ba-146">The Oracle CDC Service</span></span>](the-oracle-cdc-service.md)  
  
-   [<span data-ttu-id="b74ba-147">Servicio de captura de datos modificados para Oracle de Attunity (Ayuda de F1)</span><span class="sxs-lookup"><span data-stu-id="b74ba-147">Change Data Capture Service for Oracle by Attunity F1 Help</span></span>](change-data-capture-service-for-oracle-by-attunity-f1-help.md)  
  
-   [<span data-ttu-id="b74ba-148">Servicio de captura de datos modificados para Oracle de Attunity (Guía de procedimientos)</span><span class="sxs-lookup"><span data-stu-id="b74ba-148">Change Data Capture Service for Oracle by Attunity How to Guide</span></span>](change-data-capture-service-for-oracle-by-attunity-how-to-guide.md)  
  
## <a name="see-also"></a><span data-ttu-id="b74ba-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b74ba-149">See Also</span></span>  
 [<span data-ttu-id="b74ba-150">Trabajar con el servicio CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="b74ba-150">Working with the Oracle CDC Service</span></span>](working-with-the-oracle-cdc-service.md)  
  
  
