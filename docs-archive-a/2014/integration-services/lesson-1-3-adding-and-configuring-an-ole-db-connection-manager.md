---
title: 'Paso 3: Agregar y configurar un administrador de conexiones OLE DB | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7b74cba-a0e5-4478-af12-3f81b9484e9e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3bc4c885ce6c39c72031dd3b528a769cd47ac8f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673137"
---
# <a name="step-3-adding-and-configuring-an-ole-db-connection-manager"></a><span data-ttu-id="fa9bc-102">Paso 3: Adición y configuración de un administrador de conexiones OLE DB</span><span class="sxs-lookup"><span data-stu-id="fa9bc-102">Step 3: Adding and Configuring an OLE DB Connection Manager</span></span>
  <span data-ttu-id="fa9bc-103">Una vez que haya agregado un administrador de conexiones de archivos planos al origen de datos, la siguiente tarea consiste en agregar un administrador de conexiones OLE DB para conectarse al destino.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-103">After you have added a Flat File connection manager to connect to the data source, the next task is to add an OLE DB connection manager to connect to the destination.</span></span> <span data-ttu-id="fa9bc-104">Un administrador de conexiones OLE DB permite a un paquete extraer datos de un origen de datos compatible con OLE DB o cargar datos en este origen de datos.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-104">An OLE DB connection manager enables a package to extract data from or load data into any OLE DB-compliant data source.</span></span> <span data-ttu-id="fa9bc-105">Mediante el administrador de conexiones OLE DB, puede especificar el servidor, el método de autenticación y la base de datos predeterminada de la conexión.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-105">Using the OLE DB Connection manager, you can specify the server, the authentication method, and the default database for the connection.</span></span>  
  
 <span data-ttu-id="fa9bc-106">En esta lección, creará un administrador de conexiones OLE DB que usa la Autenticación de Windows para conectarse a la instancia local de **AdventureWorksDB2012**.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-106">In this lesson, you will create an OLE DB connection manager that uses Windows Authentication to connect to the local instance of **AdventureWorksDB2012**.</span></span> <span data-ttu-id="fa9bc-107">Otros componentes que creará más adelante en este tutorial, como la transformación Búsqueda y el destino de OLE DB, también harán referencia al administrador de conexiones OLE DB que cree.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-107">The OLE DB connection manager that you create will also be referenced by other components that you will create later in this tutorial, such as the Lookup transformation and the OLE DB destination.</span></span>  
  
### <a name="to-add-and-configure-an-ole-db-connection-manager-to-the-ssis-package"></a><span data-ttu-id="fa9bc-108">Para agregar y configurar un administrador de conexiones de OLE DB para el paquete SSIS</span><span class="sxs-lookup"><span data-stu-id="fa9bc-108">To add and configure an OLE DB Connection Manager to the SSIS package</span></span>  
  
1.  <span data-ttu-id="fa9bc-109">Haga clic con el botón derecho en cualquier punto del área **Administradores de conexión** y luego haga clic en **Nueva conexión OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-109">Right-click anywhere in the **Connection Managers** area, and then click **New OLE DB Connection**.</span></span>  
  
2.  <span data-ttu-id="fa9bc-110">En el cuadro de diálogo **Configurar el administrador de conexiones OLE DB** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-110">In the **Configure OLE DB Connection Manager** dialog box, click **New**.</span></span>  
  
3.  <span data-ttu-id="fa9bc-111">En **Nombre del servidor**, escriba **localhost**.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-111">For **Server name**, enter **localhost**.</span></span>  
  
     <span data-ttu-id="fa9bc-112">Cuando se especifica localhost como el nombre del servidor, el administración de conexión se conecta a la instancia predeterminada de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-112">When you specify localhost as the server name, the connection manager connects to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="fa9bc-113">Para usar una instancia remota de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], sustituya localhost con el nombre del servidor al que desea conectarse.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-113">To use a remote instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], replace localhost with the name of the server to which you want to connect.</span></span>  
  
4.  <span data-ttu-id="fa9bc-114">En el grupo **Iniciar sesión en el servidor** , compruebe que la opción **Usar autenticación de Windows** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-114">In the **Log on to the server** group, verify that **Use Windows Authentication** is selected.</span></span>  
  
5.  <span data-ttu-id="fa9bc-115">En el grupo **conectarse a una base de datos** , en el cuadro **Seleccione o escriba un nombre de base de datos** , escriba o seleccione `AdventureWorksDW2012` .</span><span class="sxs-lookup"><span data-stu-id="fa9bc-115">In the **Connect to a database** group, in the **Select or enter a database name** box, type or select `AdventureWorksDW2012`.</span></span>  
  
6.  <span data-ttu-id="fa9bc-116">Haga clic en **Probar conexión** para comprobar si los parámetros de conexión que ha especificado son válidos.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-116">Click **Test Connection** to verify that the connection settings you have specified are valid.</span></span>  
  
7.  <span data-ttu-id="fa9bc-117">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-117">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="fa9bc-118">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="fa9bc-119">En el panel **Conexiones de datos** del cuadro de diálogo **Configurar el administrador de conexiones OLE DB** , compruebe que la opción **localhost.AdventureWorksDW2012** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-119">In the **Data Connections** pane of the **Configure OLE DB Connection Manager** dialog box, verify that **localhost.AdventureWorksDW2012** is selected.</span></span>  
  
10. <span data-ttu-id="fa9bc-120">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa9bc-120">Click **OK**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="fa9bc-121">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="fa9bc-121">Next Task in Lesson</span></span>  
 [<span data-ttu-id="fa9bc-122">Paso 4: Adición de una tarea Flujo de datos al paquete</span><span class="sxs-lookup"><span data-stu-id="fa9bc-122">Step 4: Adding a Data Flow Task to the Package</span></span>](lesson-1-4-adding-a-data-flow-task-to-the-package.md)  
  
## <a name="see-also"></a><span data-ttu-id="fa9bc-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa9bc-123">See Also</span></span>  
 [<span data-ttu-id="fa9bc-124">Administrador de conexiones OLE DB</span><span class="sxs-lookup"><span data-stu-id="fa9bc-124">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
