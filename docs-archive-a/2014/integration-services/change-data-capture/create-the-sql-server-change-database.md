---
title: Crear la base de datos de cambios de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraIns
ms.assetid: 4f79c24a-e99a-4a06-8637-51eeec406259
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0eaeb26d5bea4c9e50db29aaa45297ba763dbbfa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749402"
---
# <a name="create-the-sql-server-change-database"></a><span data-ttu-id="de4d8-102">Crear la base de datos de cambios de SQL Server</span><span class="sxs-lookup"><span data-stu-id="de4d8-102">Create the SQL Server Change Database</span></span>
  <span data-ttu-id="de4d8-103">Cuando se inicia el Asistente para nueva instancia, se abre la página Crear base de datos CDC.</span><span class="sxs-lookup"><span data-stu-id="de4d8-103">When you start the New Instance wizard, the Create CDC Database page opens.</span></span> <span data-ttu-id="de4d8-104">Use la página Crear base de datos CDC para proporcionar información sobre la nueva instancia CDC y crear una nueva base de datos Cambios.</span><span class="sxs-lookup"><span data-stu-id="de4d8-104">Use the Create CDC Database page to provide information about the new CDC instance and create a new Change database.</span></span>  
  
 <span data-ttu-id="de4d8-105">Cuando se crea una nueva base de datos CDC, se habilita para CDC de SQL Server y esta habilitación necesita un inicio de sesión que sea miembro del rol fijo de servidor `sysadmin` .</span><span class="sxs-lookup"><span data-stu-id="de4d8-105">When you create a new CDC database it is enabled for SQL Server CDC and this enablement requires a login that is a member of the `sysadmin` fixed-server role.</span></span>  
  
 <span data-ttu-id="de4d8-106">Cuando un usuario que inicia el Asistente para crear una instancia CDC de Oracle no es miembro del rol fijo de servidor `sysadmin` , se abre el cuadro de diálogo Conectar con SQL Server y solicita las credenciales para un miembro del rol sysadmin para realizar la tarea Habilitar la base de datos para CDC de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="de4d8-106">When a user that starts the Create an Oracle CDC Instance wizard is not a member of the `sysadmin` fixed-server role, the Connect to SQL Server dialog box opens and requests the credentials for a member of the sysadmin role to carry out the Enable the database for SQL Server CDC task.</span></span> <span data-ttu-id="de4d8-107">Cuando se crea la base de datos CDC, el inicio de sesión `sysadmin` se descarta y se reanuda el trabajo con el inicio de sesión original de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usado cuando se entró en la Consola del diseñador de Oracle.</span><span class="sxs-lookup"><span data-stu-id="de4d8-107">When the CDC database is created, the `sysadmin` login is discarded and work resumes with the original [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used when the Oracle Designer Console was entered.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="de4d8-108">Para otras tareas distintas de Habilitar la base de datos para CDC de SQL Server, el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usado para ejecutar el Asistente para nueva instancia debe tener el rol fijo de servidor `dbcreator` y permisos UPDATE en la base de datos MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="de4d8-108">For tasks other than Enable the database for SQL Server CDC of, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used for running the New Instance Wizard must have the `dbcreator` fixed-server role and UPDATE permissions on the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="de4d8-109">Para obtener información acerca de cómo escribir los datos en el cuadro de diálogo Conectar con SQL Server, vea [SQL Server Connection for Instance Creation](sql-server-connection-for-instance-creation.md).</span><span class="sxs-lookup"><span data-stu-id="de4d8-109">For information on entering the data in the Connect to SQL Server dialog box, see [SQL Server Connection for Instance Creation](sql-server-connection-for-instance-creation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="de4d8-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="de4d8-110">Options</span></span>  
 <span data-ttu-id="de4d8-111">**Instancia CDC de Oracle**</span><span class="sxs-lookup"><span data-stu-id="de4d8-111">**Oracle CDC Instance**</span></span>  
 <span data-ttu-id="de4d8-112">Escriba la siguiente información sobre la instancia de CDC que está creando.</span><span class="sxs-lookup"><span data-stu-id="de4d8-112">Type the following information about the CDC instance you are creating.</span></span>  
  
-   <span data-ttu-id="de4d8-113">**Nombre**: escriba un nombre para el nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="de4d8-113">**Name**: Type a name for the new service.</span></span> <span data-ttu-id="de4d8-114">También será el nombre de la nueva base de datos Cambios.</span><span class="sxs-lookup"><span data-stu-id="de4d8-114">This will also be the name of the new Change database.</span></span>  
  
-   <span data-ttu-id="de4d8-115">**Descripción**: escriba una descripción de la nueva instancia como ayuda para identificarla.</span><span class="sxs-lookup"><span data-stu-id="de4d8-115">**Description**: Type a description for the new instance to help you identify it.</span></span> <span data-ttu-id="de4d8-116">Esto es opcional.</span><span class="sxs-lookup"><span data-stu-id="de4d8-116">This is optional.</span></span>  
  
 <span data-ttu-id="de4d8-117">**Base de datos de cambios de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="de4d8-117">**SQL Server Change Database**</span></span>  
 <span data-ttu-id="de4d8-118">Esta sección se emplea para crear la base de datos.</span><span class="sxs-lookup"><span data-stu-id="de4d8-118">This section is used to create the database.</span></span>  
  
1.  <span data-ttu-id="de4d8-119">**Base de datos de cambios**: el nombre de la nueva base de datos de cambios.</span><span class="sxs-lookup"><span data-stu-id="de4d8-119">**Change Database**: The name of the new Change database.</span></span> <span data-ttu-id="de4d8-120">El nombre de la base de datos es el mismo que el que asignó a la instancia.</span><span class="sxs-lookup"><span data-stu-id="de4d8-120">The name of the database is the same as the name that you gave to the instance.</span></span> <span data-ttu-id="de4d8-121">Este campo de solo lectura muestra la ruta de acceso completa a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="de4d8-121">This read-only field displays the full path to the database.</span></span>  
  
2.  <span data-ttu-id="de4d8-122">**Crear base de datos**: haga clic en **Crear base de datos** para crear la base de datos.</span><span class="sxs-lookup"><span data-stu-id="de4d8-122">**Create Database**: Click **Create Database** to create the database.</span></span>  
  
     <span data-ttu-id="de4d8-123">Para crear la base de datos, el inicio de sesión debe tener el rol de servidor `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="de4d8-123">To create the database, the login must have the `sysasmin` server role.</span></span> <span data-ttu-id="de4d8-124">Vea la nota de seguridad anterior para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="de4d8-124">See the security note above for more information.</span></span>  
  
     <span data-ttu-id="de4d8-125">Después de crear la base de datos, puede hacer clic en **Siguiente** para [Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md).</span><span class="sxs-lookup"><span data-stu-id="de4d8-125">After you create the database, you can click **Next** to [Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de4d8-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de4d8-126">See Also</span></span>  
 <span data-ttu-id="de4d8-127">[Cómo crear la instancia de base de datos de cambios de SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="de4d8-127">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="de4d8-128">El servicio CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="de4d8-128">The Oracle CDC Service</span></span>](the-oracle-cdc-service.md)  
  
  
