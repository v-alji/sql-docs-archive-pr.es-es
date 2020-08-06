---
title: Cómo preparar SQL Server para CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a327fa18-58f4-4e69-bb87-44faf47e20ef
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fbd285faaa55a28ad82beb673fa783570809bd04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743611"
---
# <a name="how-to-prepare-sql-server-for-cdc"></a><span data-ttu-id="752ce-102">Cómo preparar SQL Server para CDC</span><span class="sxs-lookup"><span data-stu-id="752ce-102">How to Prepare SQL Server for CDC</span></span>
  <span data-ttu-id="752ce-103">El servicio CDC de Oracle necesita que todas las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino contengan la base de datos MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="752ce-103">The Oracle CDC service requires all target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances to contain the MSXDBCDC database.</span></span> <span data-ttu-id="752ce-104">Esta base de datos se crea mediante la acción Preparar SQL Server de la Consola de configuración del servicio CDC. Esta tarea se realiza una sola vez para cada instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de destino.</span><span class="sxs-lookup"><span data-stu-id="752ce-104">You create this database using the Prepare SQL Server action in the CDC Service Configuration Console.This task is done one time only for each target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="752ce-105">A continuación se describe cómo preparar una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la captura de datos modificados de Oracle mediante la Consola de configuración del servicio CDC.</span><span class="sxs-lookup"><span data-stu-id="752ce-105">The following describes how to prepare a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for Oracle Change Data Capture using the CDC Service Configuration Console.</span></span> <span data-ttu-id="752ce-106">Este proceso crea la base de datos MSXDBCDC y define las tablas, los procedimientos almacenados y otros artefactos necesarios.</span><span class="sxs-lookup"><span data-stu-id="752ce-106">This process creates the MSXDBCDC database and defines the required tables, stored procedures, and other required artifacts.</span></span>  
  
 <span data-ttu-id="752ce-107">La preparación de SQL Server para CDC de Oracle se realiza mediante el administrador del servicio CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="752ce-107">Preparing the SQL Server for Oracle CDC is done by the Oracle CDC Service Administrator.</span></span> <span data-ttu-id="752ce-108">Para obtener más información acerca del rol de administrador del servicio CDC, vea [roles de usuario para Change Data Capture Service para Oracle por Attunity](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="752ce-108">For more information about the CDC Service Administrator role, see [User Roles for Change Data Capture Service for Oracle by Attunity](user-roles.md).</span></span>  
  
### <a name="to-enable-sql-server-for-cdc"></a><span data-ttu-id="752ce-109">Para habilitar SQL Server para CDC</span><span class="sxs-lookup"><span data-stu-id="752ce-109">To enable SQL Server for CDC</span></span>  
  
1.  <span data-ttu-id="752ce-110">En el menú **Inicio** , seleccione **Configuración del servicio CDC para Oracle**.</span><span class="sxs-lookup"><span data-stu-id="752ce-110">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="752ce-111">En el panel izquierdo, seleccione **Servicios CDC locales** y a continuación, en el panel **Acciones** , haga clic en **Preparar SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="752ce-111">From the left pane, select **Local CDC Services** then from the **Actions** pane, click **Prepare SQL Server**.</span></span>  
  
     <span data-ttu-id="752ce-112">También puede hacer clic con el botón derecho en **Local CDC Services** (Servicios CDC locales) y seleccionar **Prepare SQL Server**(Preparar SQL Server).</span><span class="sxs-lookup"><span data-stu-id="752ce-112">You can also right-click **Local CDC Services** and select **Prepare SQL Server**.</span></span>  
  
3.  <span data-ttu-id="752ce-113">Escriba la información necesaria en el cuadro de diálogo Preparando instancia de SQL Server para CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="752ce-113">Enter the required information in the Preparing SQL Server Instance for Oracle CDC dialog box.</span></span> <span data-ttu-id="752ce-114">Para obtener información acerca de cómo especificar la información necesaria en este cuadro de diálogo, vea [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="752ce-114">For information on how to enter the required information into this dialog box, see [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span></span>  
  
     <span data-ttu-id="752ce-115">Para preparar la instancia de SQL Server para CDC de Oracle, el inicio de sesión debe tener permiso de escritura para la base de datos MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="752ce-115">To Prepare the SQL Server instance for Oracle CDC, the login must have write permission to the MSXDBCDC database.</span></span> <span data-ttu-id="752ce-116">Escriba las credenciales para un inicio de sesión que tenga permiso de escritura para la base de datos MSXDBCDC, como un miembro del rol `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="752ce-116">Enter the credentials for a login that has write permission to the MSXDBCDC database, such as a member of the `sysasmin` role.</span></span>  
  
 <span data-ttu-id="752ce-117">**Nota**: Puede hacer clic en **Ver script** para ver una versión de solo lectura del script de configuración.</span><span class="sxs-lookup"><span data-stu-id="752ce-117">**Note**: You can click **View Script** to view a read-only version of the setup script.</span></span> <span data-ttu-id="752ce-118">Un administrador del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede copiar este script en la consola de administración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para editarlo y ejecutarlo, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="752ce-118">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator can copy this script into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Console to edit and execute it, if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="752ce-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="752ce-119">See Also</span></span>  
 [<span data-ttu-id="752ce-120">Preparar SQL Server para CDC</span><span class="sxs-lookup"><span data-stu-id="752ce-120">Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
