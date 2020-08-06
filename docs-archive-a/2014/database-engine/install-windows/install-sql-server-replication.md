---
title: Instalar la replicación de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- components [SQL Server replication]
- command line installations [SQL Server replication]
- installing replication
- replication [SQL Server], installing
- command prompt [SQL Server replication]
ms.assetid: c50ad078-060b-4a8d-ad45-9e31a8d85729
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ba941fda1d463e7bb4a26bd2fbb45d2a82ca27b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744838"
---
# <a name="install-sql-server-replication"></a><span data-ttu-id="e7cee-102">Instalar la replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e7cee-102">Install SQL Server Replication</span></span>
  <span data-ttu-id="e7cee-103">Los componentes de replicación se pueden instalar mediante el Asistente para la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e7cee-103">Replication components can be installed by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard or at a command prompt.</span></span> <span data-ttu-id="e7cee-104">Instale la replicación al instalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]o al modificar una instancia existente.</span><span class="sxs-lookup"><span data-stu-id="e7cee-104">Install replication when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or when you modify an existing instance.</span></span>  
  
 <span data-ttu-id="e7cee-105">Después de instalar los componentes de replicación, debe configurar el servidor antes de poder utilizar la replicación.</span><span class="sxs-lookup"><span data-stu-id="e7cee-105">After replication components are installed, you must configure the server before you can use replication.</span></span> <span data-ttu-id="e7cee-106">Para obtener más información, vea [Configurar la distribución](../../relational-databases/replication/configure-distribution.md) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7cee-106">For more information, see [Configure Distribution](../../relational-databases/replication/configure-distribution.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e7cee-107">Si instala componentes de replicación al modificar una instancia existente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], debe detener y reiniciar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] una vez completada la instalación.</span><span class="sxs-lookup"><span data-stu-id="e7cee-107">If you install replication components when you modify an existing instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent after the installation is completed.</span></span> <span data-ttu-id="e7cee-108">De esta forma contribuye a asegurarse de que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] reconozca los subsistemas del agente de replicación y pueda llamar a los agentes de replicación mediante pasos de trabajos.</span><span class="sxs-lookup"><span data-stu-id="e7cee-108">This action helps ensure that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent recognizes the replication agent subsystems and can call replication agents from job steps.</span></span>  
  
## <a name="installing-replication-by-using-setup"></a><span data-ttu-id="e7cee-109">Instalar la replicación mediante el programa de instalación</span><span class="sxs-lookup"><span data-stu-id="e7cee-109">Installing Replication by Using Setup</span></span>  
 <span data-ttu-id="e7cee-110">**Para instalar la replicación al instalar una nueva instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="e7cee-110">**To install replication when installing a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span></span>  
  
-   <span data-ttu-id="e7cee-111">Para instalar componentes de replicación, incluido Replication Management Objects (RMO), seleccione **Replicación de SQL Server** en la página **Selección de características** del Asistente para la instalación.</span><span class="sxs-lookup"><span data-stu-id="e7cee-111">To install replication components, including Replication Management Objects (RMO), select **SQL Server Replication** on the **Feature Selection** page of the Installation Wizard.</span></span>  
  
## <a name="installing-replication-from-the-command-prompt"></a><span data-ttu-id="e7cee-112">Instalar la replicación desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="e7cee-112">Installing Replication from the Command Prompt</span></span>  
 <span data-ttu-id="e7cee-113">**Para instalar la replicación al instalar una nueva instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="e7cee-113">**To install replication when installing a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span></span>  
  
-   <span data-ttu-id="e7cee-114">Consulte [Install SQL Server 2014 desde el símbolo del sistema](install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="e7cee-114">See [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7cee-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e7cee-115">See Also</span></span>  
 <span data-ttu-id="e7cee-116">[Instalación de SQL Server 2014](install-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e7cee-116">[Install SQL Server 2014](install-sql-server.md) </span></span>  
 <span data-ttu-id="e7cee-117">[Instalación de SQL Server 2014 desde el símbolo del sistema](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="e7cee-117">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 [<span data-ttu-id="e7cee-118">Características admitidas por las ediciones de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="e7cee-118">Features Supported by the Editions of SQL Server 2014</span></span>](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
  
