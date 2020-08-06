---
title: Acceso a datos para las operaciones de DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 88dfb9ea-6321-4eaf-b9e4-45d36ef048f6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 515b087a8d16e44314d1a21d3dfbd6f13c767f5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746558"
---
# <a name="access-data-for-the-dqs-operations"></a><span data-ttu-id="cf3a5-102">Acceso a datos para las operaciones de DQS</span><span class="sxs-lookup"><span data-stu-id="cf3a5-102">Access Data for the DQS Operations</span></span>
  <span data-ttu-id="cf3a5-103">Para usar los datos de origen para las operaciones del [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) y exportar los datos procesados, puede realizar una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="cf3a5-103">To use your source data for [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) operations, and export your processed data, you can do either of the following:</span></span>  
  
-   <span data-ttu-id="cf3a5-104">Copie los datos de origen en una tabla o una vista en la base de datos DQS_STAGING_DATA y utilícelos posteriormente en las operaciones de DQS.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-104">Copy your source data to a table/view in the DQS_STAGING_DATA database, and then use it for DQS operations.</span></span> <span data-ttu-id="cf3a5-105">También puede exportar los datos procesados a una nueva tabla de la base de datos DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-105">You can also export the processed data to a new table in the DQS_STAGING_DATA database.</span></span> <span data-ttu-id="cf3a5-106">Para ello, se debe conceder acceso de lectura y escritura a su cuenta de usuario de Windows en la base de datos DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-106">To do so, your Windows user account must be granted read/write access to the DQS_STAGING_DATA database.</span></span>  
  
-   <span data-ttu-id="cf3a5-107">Use su propia base de datos como datos de origen para las operaciones de DQS y como destino para exportar los datos procesados.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-107">Use your own database as the source data for the DQS operations, and destination for exporting the processed data.</span></span> <span data-ttu-id="cf3a5-108">Para ello, asegúrese de que la base de datos está en la misma instancia de SQL Server que las bases de datos de Data Quality Server.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-108">To do so, ensure that your database is in the same SQL Server instance as the Data Quality Server databases.</span></span> <span data-ttu-id="cf3a5-109">De lo contrario, la base de datos no estará disponible en Data Quality Client para las operaciones de DQS.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-109">Otherwise, the database will not be available in the Data Quality Client for DQS operations.</span></span> <span data-ttu-id="cf3a5-110">Además, se debe conceder acceso a la cuenta de usuario de Windows en la base de datos DQS_STAGING_DATA para exportar los resultados coincidentes, ya que estos se exportan en dos fases: primero, los resultados coincidentes se exportan a las tablas temporales de la base de datos DQS_STAGING_DATA y, después, se mueven a la tabla de la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-110">Also, your Windows user account must be granted access on the DQS_STAGING_DATA database for exporting the matching results because matching results are exported in two phases: first, the matching results are exported to the temporary tables in the DQS_STAGING_DATA database, and then moved to the table in your destination database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cf3a5-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cf3a5-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="cf3a5-112">Debe haber completado la instalación del [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] ejecutando el archivo DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-112">You must have completed the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="cf3a5-113">Para obtener más información, vea [Ejecutar DQSInstaller.exe para completar la instalación del servidor de calidad de datos](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="cf3a5-113">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
-   <span data-ttu-id="cf3a5-114">La cuenta de usuario de Windows debe ser miembro del rol fijo de servidor apropiado (como securityadmin, serveradmin o sysadmin) en la instancia del motor de base de datos para conceder o modificar el acceso al inicio de sesión de SQL en las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-114">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) in the database engine instance to grant/modify access to SQL login on databases.</span></span>  
  
### <a name="to-grant-readwrite-access-to-a-user-on-the-dqs_staging_data-database"></a><span data-ttu-id="cf3a5-115">Para conceder acceso de lectura y escritura a un usuario en la base de datos DQS_STAGING_DATA</span><span class="sxs-lookup"><span data-stu-id="cf3a5-115">To grant read/write access to a User on the DQS_STAGING_DATA Database</span></span>  
  
1.  <span data-ttu-id="cf3a5-116">Inicie Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-116">Start Microsoft SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="cf3a5-117">En Microsoft SQL Server Management Studio, expanda la instancia de SQL Server y, a continuación, expanda **Seguridad**e **Inicios de sesión**.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-117">In Microsoft SQL Server Management Studio, expand your SQL Server instance, and expand **Security**, and then expand **Logins**.</span></span>  
  
3.  <span data-ttu-id="cf3a5-118">Haga clic con el botón derecho en el inicio de sesión de SQL y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-118">Right-click a SQL login, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="cf3a5-119">En el cuadro de diálogo **Propiedades de inicio de sesión** , haga clic en la página **Asignación de usuarios** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-119">In the **Login Properties** dialog box, click the **User Mapping** page in the left pane.</span></span>  
  
5.  <span data-ttu-id="cf3a5-120">En el panel derecho, seleccione la casilla en la columna **Asignar** para la base de datos **DQS_STAGING_DATA** y, después, seleccione los siguientes roles en el panel **Pertenencia al rol de base de datos para: DQS_STAGING_DATA** :</span><span class="sxs-lookup"><span data-stu-id="cf3a5-120">In the right pane, select the check box under the **Map** column for the **DQS_STAGING_DATA** database, and then select the following roles in the **Database role membership for: DQS_STAGING_DATA** pane:</span></span>  
  
    -   <span data-ttu-id="cf3a5-121">**db_datareader**: leer datos de las tablas y de las vistas.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-121">**db_datareader**: Read data from tables/views.</span></span>  
  
    -   <span data-ttu-id="cf3a5-122">**db_datawriter**: agregar, eliminar o cambiar los datos de las tablas.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-122">**db_datawriter**: Add, delete, or change data in tables.</span></span>  
  
    -   <span data-ttu-id="cf3a5-123">**db_ddladmin**: crear, modificar o eliminar las tablas o vistas.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-123">**db_ddladmin**: Create, modify, or delete tables/views.</span></span>  
  
6.  <span data-ttu-id="cf3a5-124">En el cuadro de diálogo **Propiedades de inicio de sesión** , haga clic en **Aceptar** para aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-124">In the **Login Properties** dialog box, click **OK** to apply the changes.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cf3a5-125">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="cf3a5-125">Next Steps</span></span>  
 <span data-ttu-id="cf3a5-126">Intente realizar operaciones de DQS que obtengan acceso a la base de datos como origen de datos para la operación de DQS, y después exporte los datos procesados a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cf3a5-126">Try performing DQS operations that accesses the database as data source for DQS operation, and then exports the processed data to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf3a5-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cf3a5-127">See Also</span></span>  
 [<span data-ttu-id="cf3a5-128">Instalar Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="cf3a5-128">Install Data Quality Services</span></span>](install-data-quality-services.md)  
  
  
