---
title: 'Lección 7: trasladar los archivos de datos a Azure Storage | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 26aa534a-afe7-4a14-b99f-a9184fc699bd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 753863d7b8b8d8fa554f1579bee6837c525efd9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675363"
---
# <a name="lesson-7-move-your-data-files-to-azure-storage"></a><span data-ttu-id="2e12e-102">Lección 7: Mover los archivos de datos a Azure Storage</span><span class="sxs-lookup"><span data-stu-id="2e12e-102">Lesson 7: Move your data files to Azure Storage</span></span>
  <span data-ttu-id="2e12e-103">En esta lección, obtendrá información sobre cómo migrar los archivos de datos a Azure Storage (pero no a la instancia de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="2e12e-103">In this lesson, you will learn how to move your data files to Azure Storage (but not your SQL Server instance).</span></span> <span data-ttu-id="2e12e-104">Para seguir esta lección, no es necesario completar las lecciones 4, 5 y 6.</span><span class="sxs-lookup"><span data-stu-id="2e12e-104">To follow this lesson, you do not need to complete Lesson 4, 5, and 6.</span></span>  
  
 <span data-ttu-id="2e12e-105">Para trasladar los archivos de datos a Azure Storage, puede usar la `ALTER DATABASE` instrucción, ya que ayuda a cambiar la ubicación de los archivos de datos.</span><span class="sxs-lookup"><span data-stu-id="2e12e-105">To move your data files to Azure Storage, you can use the `ALTER DATABASE` statement as it helps to change the location of the data files.</span></span>  
  
 <span data-ttu-id="2e12e-106">En esta lección se supone que ya completó los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2e12e-106">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="2e12e-107">Tiene una cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="2e12e-107">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="2e12e-108">Ha creado un contenedor en su cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="2e12e-108">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="2e12e-109">Ha creado una directiva en un contenedor con derechos de lectura, escritura y enumeración.</span><span class="sxs-lookup"><span data-stu-id="2e12e-109">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="2e12e-110">También generó una clave SAS.</span><span class="sxs-lookup"><span data-stu-id="2e12e-110">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="2e12e-111">Ha creado una credencial de SQL Server en el equipo de origen.</span><span class="sxs-lookup"><span data-stu-id="2e12e-111">You have created a SQL Server credential on the source machine.</span></span>  
  
 <span data-ttu-id="2e12e-112">A continuación, siga estos pasos para migrar los archivos de datos a Azure Storage:</span><span class="sxs-lookup"><span data-stu-id="2e12e-112">Next, use the following steps to move your data files to Azure Storage:</span></span>  
  
1.  <span data-ttu-id="2e12e-113">Primero, cree una base de datos de prueba en el equipo de origen y agréguele algunos datos.</span><span class="sxs-lookup"><span data-stu-id="2e12e-113">First, create a test database in the source machine and add some data to it.</span></span>  
  
    ```sql  
  
    USE master;   
    CREATE DATABASE TestDB1Alter;   
    GO   
    USE TestDB1Alter;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO  
  
    ```  
  
2.  <span data-ttu-id="2e12e-114">Ejecute el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2e12e-114">Run the following code:</span></span>  
  
    ```sql  
  
    -- In the following statement, modify the path specified in FILENAME to   
    -- the new location of the file in Azure Storage container.   
    ALTER DATABASE TestDB1Alter    
        MODIFY FILE ( NAME = TestDB1Alter,    
                    FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontaineralter/TestDB1AlterData.mdf');   
    GO  
  
    ```  
  
3.  <span data-ttu-id="2e12e-115">Al ejecutarlo, verá este mensaje: "el archivo" TestDB1Alter "se ha modificado en el catálogo del sistema.</span><span class="sxs-lookup"><span data-stu-id="2e12e-115">When you run this, you will see this message: "The file "TestDB1Alter" has been modified in the system catalog.</span></span> <span data-ttu-id="2e12e-116">La nueva ruta de acceso se utilizará la próxima vez que se inicie la base de datos ".</span><span class="sxs-lookup"><span data-stu-id="2e12e-116">The new path will be used the next time the database is started."</span></span>  
  
4.  <span data-ttu-id="2e12e-117">Después, establezca la base de datos sin conexión.</span><span class="sxs-lookup"><span data-stu-id="2e12e-117">Then, set the database offline.</span></span>  
  
    ```sql  
  
    ALTER DATABASE TestDB1Alter SET OFFLINE;   
    GO  
  
    ```  
  
5.  <span data-ttu-id="2e12e-118">Ahora, debe copiar los archivos de datos en Azure Storage con uno de los métodos siguientes: [herramienta AzCopy](https://docs.microsoft.com/archive/blogs/windowsazurestorage/azcopy-uploadingdownloading-files-for-windows-azure-blobs), [Página Put](https://msdn.microsoft.com/library/azure/ee691975.aspx), referencia de la [biblioteca de cliente de almacenamiento](https://msdn.microsoft.com/library/azure/dn261237.aspx)o una herramienta de explorador de almacenamiento de terceros.</span><span class="sxs-lookup"><span data-stu-id="2e12e-118">Now, you need to copy the data files to Azure Storage by using one of the following methods: [AzCopy Tool](https://docs.microsoft.com/archive/blogs/windowsazurestorage/azcopy-uploadingdownloading-files-for-windows-azure-blobs), [Put Page](https://msdn.microsoft.com/library/azure/ee691975.aspx), [Storage Client Library Reference](https://msdn.microsoft.com/library/azure/dn261237.aspx), or a third-party storage explorer tool.</span></span>  
  
     <span data-ttu-id="2e12e-119">**Importante:** Al usar esta nueva mejora, asegúrese siempre de que crea un BLOB en páginas y no un BLOB en bloques.</span><span class="sxs-lookup"><span data-stu-id="2e12e-119">**Important:** When using this new enhancement, always make sure that you create a page blob not a block blob.</span></span>  
  
6.  <span data-ttu-id="2e12e-120">Después, establezca la base de datos con conexión.</span><span class="sxs-lookup"><span data-stu-id="2e12e-120">Then, set the database online.</span></span>  
  
    ```sql  
  
    ALTER DATABASE TestDB1Alter SET ONLINE;   
    GO  
  
    ```  
  
 <span data-ttu-id="2e12e-121">**Lección siguiente:**</span><span class="sxs-lookup"><span data-stu-id="2e12e-121">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="2e12e-122">Lección 8. Restaurar una base de datos a Azure Storage</span><span class="sxs-lookup"><span data-stu-id="2e12e-122">Lesson 8. Restore a database to Azure Storage</span></span>](lesson-7-restore-a-database-to-a-point-in-time.md)  
  
  
