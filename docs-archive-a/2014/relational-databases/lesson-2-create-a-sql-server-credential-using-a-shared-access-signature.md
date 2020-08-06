---
title: 'Lección 3: crear una credencial de SQL Server | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 29e57ebd-828f-4dff-b473-c10ab0b1c597
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 808438e544e3beb18b2e2afa9c399b5666277483
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749303"
---
# <a name="lesson-3-create-a-sql-server-credential"></a><span data-ttu-id="c04d9-102">Lección 3: Crear una credencial de SQL Server</span><span class="sxs-lookup"><span data-stu-id="c04d9-102">Lesson 3: Create a SQL Server Credential</span></span>
  <span data-ttu-id="c04d9-103">En esta lección, creará una credencial para almacenar la información de seguridad que se usa para acceder a la cuenta de almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="c04d9-103">In this lesson, you will create a credential to store security information used to access the Azure storage account.</span></span>  
  
 <span data-ttu-id="c04d9-104">Una credencial de SQL Server es un objeto que se usa para almacenar la información de autenticación necesaria para conectarse a un recurso fuera de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c04d9-104">A SQL Server credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span> <span data-ttu-id="c04d9-105">La credencial almacena la ruta de acceso de URI de los valores clave de la signatura de acceso compartida y el contenedor de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="c04d9-105">The credential stores the URI path of the storage container and the shared access signature key values.</span></span> <span data-ttu-id="c04d9-106">Para cada contenedor de almacenamiento utilizado por un archivo de datos o de registro, debe crear una credencial de SQL Server cuyo nombre coincida con la ruta de acceso del contenedor.</span><span class="sxs-lookup"><span data-stu-id="c04d9-106">For each storage container used by a data or log file, you must create a SQL Server Credential whose name matches the container path.</span></span>  
  
 <span data-ttu-id="c04d9-107">Para obtener información general sobre las credenciales, vea [credenciales &#40;Motor de base de datos&#41;](security/authentication-access/credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="c04d9-107">For general information about credentials, see [Credentials &#40;Database Engine&#41;](security/authentication-access/credentials-database-engine.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c04d9-108">Los requisitos para crear una credencial SQL Server que se describe a continuación son específicos de la característica [archivos de datos de SQL Server en Azure](databases/sql-server-data-files-in-microsoft-azure.md) .</span><span class="sxs-lookup"><span data-stu-id="c04d9-108">The requirements for creating a SQL Server credential described below are specific to the [SQL Server Data Files in Azure](databases/sql-server-data-files-in-microsoft-azure.md) feature.</span></span> <span data-ttu-id="c04d9-109">Para información sobre cómo crear credenciales para los procesos de copias de seguridad en el almacenamiento de Azure, vea [Lesson 2: Create a SQL Server Credential](../tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="c04d9-109">For information on creating credentials for backup processes in Azure storage, see [Lesson 2: Create a SQL Server Credential](../tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
 <span data-ttu-id="c04d9-110">Para crear una credencial de SQL Server, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c04d9-110">To create a SQL Server Credential, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c04d9-111">Conéctese a SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="c04d9-111">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="c04d9-112">En el Explorador de objetos, conéctese a la instancia del Motor de base de datos instalado.</span><span class="sxs-lookup"><span data-stu-id="c04d9-112">In Object Explorer, connect to the instance of Database Engine installed.</span></span>  
  
3.  <span data-ttu-id="c04d9-113">En la barra de herramientas Estándar, haga clic en Nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="c04d9-113">On the Standard tool bar, click New Query.</span></span>  
  
4.  <span data-ttu-id="c04d9-114">Copie y pegue el ejemplo siguiente en la ventana de consulta, y modifíquelo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c04d9-114">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="c04d9-115">La siguiente instrucción creará una credencial SQL Server para almacenar el certificado de acceso compartido del contenedor de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="c04d9-115">The following statement will create a SQL Server Credential to store your storage container's Shared Access Certificate.</span></span>  
  
    ```sql  
  
    USE master  
    CREATE CREDENTIAL credentialname - this name should match the container path and it must start with https.   
       WITH IDENTITY='SHARED ACCESS SIGNATURE', -- this is a mandatory string and do not change it.   
       SECRET = 'sharedaccesssignature' -- this is the shared access signature key that you obtained in Lesson 2.   
    GO  
  
    ```  
  
     <span data-ttu-id="c04d9-116">Para obtener información detallada, consulte [Create CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) en libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c04d9-116">For detailed information, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) in SQL Server Books Online.</span></span>  
  
5.  <span data-ttu-id="c04d9-117">Para ver todas las credenciales disponibles, puede ejecutar la siguiente instrucción en la ventana de consulta:</span><span class="sxs-lookup"><span data-stu-id="c04d9-117">To see all available credentials, you can run the following statement in the query window:</span></span>  
  
    ```sql  
    SELECT * from sys.credentials  
    ```  
  
     <span data-ttu-id="c04d9-118">Para obtener más información sobre sys. Credentials, vea [Sys. credentials &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) en libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c04d9-118">For more information on sys.credentials, see [sys.credentials &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="c04d9-119">**Lección siguiente:**</span><span class="sxs-lookup"><span data-stu-id="c04d9-119">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="c04d9-120">Lección 4: Crear una base de datos en Azure Storage</span><span class="sxs-lookup"><span data-stu-id="c04d9-120">Lesson 4: Create a database in Azure Storage</span></span>](lesson-3-database-backup-to-url.md)  
  
  
