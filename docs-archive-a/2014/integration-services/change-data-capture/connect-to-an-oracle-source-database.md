---
title: Conectar con una base de datos de origen de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraDb
ms.assetid: 220cf555-0db2-443c-8f87-8e413f3ca731
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fccba3d11adc67b3f5ef4f8648ec5d0de07a5648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747718"
---
# <a name="connect-to-an-oracle-source-database"></a><span data-ttu-id="db2eb-102">Conectar con una base de datos de origen de Oracle</span><span class="sxs-lookup"><span data-stu-id="db2eb-102">Connect to an Oracle Source Database</span></span>
  <span data-ttu-id="db2eb-103">Use la página Oracle Source para proporcionar la información necesaria para conectarse a la base de datos de origen de Oracle.</span><span class="sxs-lookup"><span data-stu-id="db2eb-103">Use the Oracle Source page to provide the information necessary to connect to the Oracle source database.</span></span> <span data-ttu-id="db2eb-104">La instancia CDC leerá los registros Rehacer de la base de datos de Oracle a la que está conectado.</span><span class="sxs-lookup"><span data-stu-id="db2eb-104">The CDC instance will read the redo logs of the Oracle database you are connected to.</span></span>  
  
 <span data-ttu-id="db2eb-105">**Cadena de conexión de Oracle**</span><span class="sxs-lookup"><span data-stu-id="db2eb-105">**Oracle Connect String**</span></span>  
 <span data-ttu-id="db2eb-106">Escriba la cadena de conexión de Oracle al equipo que tiene la base de datos de Oracle que está usando.</span><span class="sxs-lookup"><span data-stu-id="db2eb-106">Enter the Oracle connect string to the computer with the Oracle database you are using.</span></span> <span data-ttu-id="db2eb-107">La cadena de conexión se escribe de una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="db2eb-107">The connect string is written in one of the following ways:</span></span>  
  
 `host[:port][/service name]`  
  
 <span data-ttu-id="db2eb-108">La cadena de conexión también puede especificar un descriptor de conexión de Oracle Net, por ejemplo `(DESCRIPTION=(ADDRESS=(PROTOCOL=tcp) (HOST=erp.contoso.com) (PORT=1521)) (CONNECT_DATA=(SERVICE_NAME=orcl)))`</span><span class="sxs-lookup"><span data-stu-id="db2eb-108">The connection string can also specify an Oracle Net connect descriptor, for example, `(DESCRIPTION=(ADDRESS=(PROTOCOL=tcp) (HOST=erp.contoso.com) (PORT=1521)) (CONNECT_DATA=(SERVICE_NAME=orcl)))`</span></span>  
  
 <span data-ttu-id="db2eb-109">Si se usa un servidor de directorio o tnsnames, la cadena de conexión puede ser el nombre de la conexión.</span><span class="sxs-lookup"><span data-stu-id="db2eb-109">If using a directory server or tnsnames, the connect string can be the name of the connection.</span></span>  
  
 <span data-ttu-id="db2eb-110">**Autenticación de minería de registros de Oracle**</span><span class="sxs-lookup"><span data-stu-id="db2eb-110">**Oracle Log Mining Authentication**</span></span>  
 <span data-ttu-id="db2eb-111">Para especificar las credenciales del usuario de la base de datos de Oracle que tiene autorización para realizar minería de registros, seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="db2eb-111">To enter the credentials for the Oracle database user that is authorized for log mining, select one of the following:</span></span>  
  
-   <span data-ttu-id="db2eb-112">**Autenticación de Windows**: seleccione esta opción para usar las credenciales del dominio de Windows actual.</span><span class="sxs-lookup"><span data-stu-id="db2eb-112">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="db2eb-113">Solo puede usar esta opción si la base de datos de Oracle está configurada para usar la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="db2eb-113">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="db2eb-114">**Autenticación de Oracle**: si selecciona esta opción, debe escribir el **Nombre de usuario** y la **Contraseña** para el usuario en la base de datos de Oracle a la que se está conectando.</span><span class="sxs-lookup"><span data-stu-id="db2eb-114">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Oracle database you are connecting to.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db2eb-115">Un usuario debe tener concedidos los privilegios siguientes en la base de datos de Oracle para poder ser un usuario de minería de registros.</span><span class="sxs-lookup"><span data-stu-id="db2eb-115">A user must have the following privileges granted in the Oracle database to be a log-mining user.</span></span>  
> 
>  -   <span data-ttu-id="db2eb-116">SELECT en \<any-captured-table></span><span class="sxs-lookup"><span data-stu-id="db2eb-116">SELECT on \<any-captured-table></span></span>  
> -   <span data-ttu-id="db2eb-117">SELECT ANY TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="db2eb-117">SELECT ANY TRANSACTION</span></span>  
> -   <span data-ttu-id="db2eb-118">EXECUTE en DBMS LOGMNR</span><span class="sxs-lookup"><span data-stu-id="db2eb-118">EXECUTE on DBMS LOGMNR</span></span>  
> -   <span data-ttu-id="db2eb-119">SELECT en V$LOGMNR CONTENTS</span><span class="sxs-lookup"><span data-stu-id="db2eb-119">SELECT on V$LOGMNR CONTENTS</span></span>  
> -   <span data-ttu-id="db2eb-120">SELECT en V$ARCHIVED LOG</span><span class="sxs-lookup"><span data-stu-id="db2eb-120">SELECT on V$ARCHIVED LOG</span></span>  
> -   <span data-ttu-id="db2eb-121">SELECT en V$LOG</span><span class="sxs-lookup"><span data-stu-id="db2eb-121">SELECT on V$LOG</span></span>  
> -   <span data-ttu-id="db2eb-122">SELECT en V$LOGFILE</span><span class="sxs-lookup"><span data-stu-id="db2eb-122">SELECT on V$LOGFILE</span></span>  
> -   <span data-ttu-id="db2eb-123">SELECT en V$DATABASE</span><span class="sxs-lookup"><span data-stu-id="db2eb-123">SELECT on V$DATABASE</span></span>  
> -   <span data-ttu-id="db2eb-124">SELECT en V$THREAD</span><span class="sxs-lookup"><span data-stu-id="db2eb-124">SELECT on V$THREAD</span></span>  
> -   <span data-ttu-id="db2eb-125">SELECT en ALL INDEXES</span><span class="sxs-lookup"><span data-stu-id="db2eb-125">SELECT on ALL INDEXES</span></span>  
> -   <span data-ttu-id="db2eb-126">SELECT en ALL OBJECTS</span><span class="sxs-lookup"><span data-stu-id="db2eb-126">SELECT on ALL OBJECTS</span></span>  
> -   <span data-ttu-id="db2eb-127">SELECT en DBA OBJECTS</span><span class="sxs-lookup"><span data-stu-id="db2eb-127">SELECT on DBA OBJECTS</span></span>  
> -   <span data-ttu-id="db2eb-128">SELECT en ALL TABLES</span><span class="sxs-lookup"><span data-stu-id="db2eb-128">SELECT on ALL TABLES</span></span>  
> 
>  <span data-ttu-id="db2eb-129">Si alguno de estos privilegios no se puede conceder a un V$xxx, concédalo al V_S$xxx.</span><span class="sxs-lookup"><span data-stu-id="db2eb-129">If any of these privileges cannot be granted to a V$xxx, then grant them to the V_S$xxx.</span></span>  
  
 <span data-ttu-id="db2eb-130">**Probar conexión**</span><span class="sxs-lookup"><span data-stu-id="db2eb-130">**Test Connection**</span></span>  
 <span data-ttu-id="db2eb-131">Haga clic en **Probar conexión** para determinar si se estableció una conexión con el equipo remoto que tiene la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="db2eb-131">Click **Test Connection** to determine whether you established a connection with the remote computer that has the Oracle database.</span></span> <span data-ttu-id="db2eb-132">Aparecerá un cuadro de diálogo para informarle si la conexión se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="db2eb-132">A dialog box opens to inform you whether the connection was successful.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="db2eb-133">Debido a un problema conocido, se puede producir un error en la conexión con la base de datos de origen de Oracle si el Diseñador CDC no se ejecuta como administrador.</span><span class="sxs-lookup"><span data-stu-id="db2eb-133">Due to a known issue connection to the Oracle source database may fail if the CDC Designer is not run as an administrator.</span></span> <span data-ttu-id="db2eb-134">Si se produce un error en la conexión, cierre y reinicie el Diseñador CDC usando la opción **Ejecutar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="db2eb-134">If connection fails, close and restart the CDC Designer using the **Run as administrator** option.</span></span>  
  
 <span data-ttu-id="db2eb-135">Cuando termine de especificar información en esta página, haga clic en **Siguiente** para [Select Oracle Tables and Columns](select-oracle-tables-and-columns.md).</span><span class="sxs-lookup"><span data-stu-id="db2eb-135">After you finish entering information on this page, click **Next** to [Select Oracle Tables and Columns](select-oracle-tables-and-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db2eb-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db2eb-136">See Also</span></span>  
 <span data-ttu-id="db2eb-137">[Cómo crear la instancia de base de datos de cambios de SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="db2eb-137">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="db2eb-138">Editar propiedades de la instancia</span><span class="sxs-lookup"><span data-stu-id="db2eb-138">Edit Instance Properties</span></span>](edit-instance-properties.md)  
  
  
