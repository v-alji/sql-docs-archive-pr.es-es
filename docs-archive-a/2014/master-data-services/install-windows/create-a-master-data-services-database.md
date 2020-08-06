---
title: Crea una base de datos de Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 8373bb35-f0f9-4c3c-a53c-dfaa2ce567ac
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9ee90ac5d02489da3b411b12389e949ff3136287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669713"
---
# <a name="create-a-master-data-services-database"></a><span data-ttu-id="f7300-102">Crea una base de datos de Master Data Services</span><span class="sxs-lookup"><span data-stu-id="f7300-102">Create a Master Data Services Database</span></span>
  <span data-ttu-id="f7300-103">Cree una base de datos de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] cuando necesite una base de datos nueva que sea compatible con la aplicación web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] y el servicio web de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f7300-103">Create a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database when you need a new database to support the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application and [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f7300-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f7300-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="f7300-105">Para obtener información sobre los requisitos del equipo que hospeda la base de datos, vea [Requisitos de base de datos &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f7300-105">For information about the requirements for the computer that hosts the database, see [Database Requirements &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span></span>  
  
### <a name="to-create-a-master-data-services-database"></a><span data-ttu-id="f7300-106">Para crear una base de datos de Master Data Services</span><span class="sxs-lookup"><span data-stu-id="f7300-106">To create a Master Data Services database</span></span>  
  
1.  <span data-ttu-id="f7300-107">Abra [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7300-107">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="f7300-108">En el panel izquierdo, haga clic en **Configuración de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="f7300-108">In the left pane, click **Database Configuration**.</span></span>  
  
3.  <span data-ttu-id="f7300-109">En la página **Configuración de base de datos** , haga clic en **Crear base de datos**.</span><span class="sxs-lookup"><span data-stu-id="f7300-109">On the **Database Configuration** page, click **Create Database**.</span></span>  
  
4.  <span data-ttu-id="f7300-110">Complete el asistente **Crear base de datos** para crear y configurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f7300-110">Complete the **Create Database** wizard to create and configure the database.</span></span> <span data-ttu-id="f7300-111">Para obtener información sobre las opciones de interfaz de usuario (IU) en el asistente, vea [Asistente Crear base de datos &#40;Administrador de configuración de Master Data Services&#41;](../create-database-wizard-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f7300-111">For information about the user interface (UI) options in the wizard, see [Create Database Wizard &#40;Master Data Services Configuration Manager&#41;](../create-database-wizard-master-data-services-configuration-manager.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f7300-112">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f7300-112">Next Steps</span></span>  
  
-   <span data-ttu-id="f7300-113">Configure los parámetros del sistema para la aplicación web y de base de datos.</span><span class="sxs-lookup"><span data-stu-id="f7300-113">Configure system settings for the database and web application.</span></span> <span data-ttu-id="f7300-114">Para obtener más información, vea [Configuración del sistema &#40;Master Data Services&#41;](../system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f7300-114">For more information, see [System Settings &#40;Master Data Services&#41;](../system-settings-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="f7300-115">Cree una aplicación web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] para asociarla a esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="f7300-115">Create a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application to associate with this database.</span></span> <span data-ttu-id="f7300-116">Para obtener más información, vea [Crear una aplicación web de Master Data Manager &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f7300-116">For more information, see [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="f7300-117">Configure un plan de mantenimiento para hacer copias de seguridad de la base de datos y de los registros de transacciones.</span><span class="sxs-lookup"><span data-stu-id="f7300-117">Configure a maintenance plan to back up the database and transaction logs.</span></span> <span data-ttu-id="f7300-118">Para obtener más información, vea [Requisitos de base de datos &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f7300-118">For more information, see [Database Requirements &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7300-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f7300-119">See Also</span></span>  
 [<span data-ttu-id="f7300-120">Instalar Master Data Services</span><span class="sxs-lookup"><span data-stu-id="f7300-120">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
