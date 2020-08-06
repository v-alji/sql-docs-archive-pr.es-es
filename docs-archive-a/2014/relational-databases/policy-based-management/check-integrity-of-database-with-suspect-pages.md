---
title: Comprobación de la integridad de una base de datos con páginas sospechosas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3b1ec9fe-f6c5-46f7-aa63-6e671be1572d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3cc1f87917c78f34ec7722fa21a1a67fda40a8c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744068"
---
# <a name="check-integrity-of-database-with-suspect-pages"></a><span data-ttu-id="72c00-102">Comprobar la integridad de una base de datos con páginas sospechosas</span><span class="sxs-lookup"><span data-stu-id="72c00-102">Check Integrity of Database with Suspect Pages</span></span>
  <span data-ttu-id="72c00-103">Esta regla comprueba las bases de datos de usuario que tienen el estado de base de datos establecido en sospechoso.</span><span class="sxs-lookup"><span data-stu-id="72c00-103">This rule checks for user databases that have the database status set to suspect.</span></span> <span data-ttu-id="72c00-104">Cuando el [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] lee una página de base de datos que contiene un error 824, la página se considera sospechosa, su identificador se registra en la tabla suspect_pages de msdb y la base de datos que la contiene se establece como sospechosa.</span><span class="sxs-lookup"><span data-stu-id="72c00-104">When the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] reads a database page that contains an 824 error, the page is considered suspect, its page ID is recorded in the suspect_pages table in msdb, and the database that contains the page is set to suspect.</span></span>  
  
 <span data-ttu-id="72c00-105">El error 824 indica que se detectó un error de coherencia lógica durante una operación de lectura.</span><span class="sxs-lookup"><span data-stu-id="72c00-105">Error 824 indicates that a logical consistency error was detected during a read operation.</span></span> <span data-ttu-id="72c00-106">Este error suele indicar que los datos se han dañado debido a un componente del subsistema de E/S defectuoso.</span><span class="sxs-lookup"><span data-stu-id="72c00-106">This error frequently indicates data corruption caused by a faulty I/O subsystem component.</span></span> <span data-ttu-id="72c00-107">Se trata de una condición de error grave que amenaza la integridad de la base de datos y que se debe corregir de inmediato.</span><span class="sxs-lookup"><span data-stu-id="72c00-107">This is a severe error condition that threatens database integrity and must be corrected immediately.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="72c00-108">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="72c00-108">Best Practices Recommendations</span></span>  
  
-   <span data-ttu-id="72c00-109">Revise el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para obtener los detalles del error 824 para esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="72c00-109">Review the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log for the details of the 824 error for this database.</span></span>  
  
-   <span data-ttu-id="72c00-110">Realice una comprobación completa de coherencia de la base de datos ([DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)).</span><span class="sxs-lookup"><span data-stu-id="72c00-110">Complete a full database consistency check ([DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)).</span></span>  
  
-   <span data-ttu-id="72c00-111">Implemente las acciones del usuario que se definen en [MSSQLSERVER_824](https://go.microsoft.com/fwlink/?LinkId=81397).</span><span class="sxs-lookup"><span data-stu-id="72c00-111">Implement the user actions that are defined in [MSSQLSERVER_824](https://go.microsoft.com/fwlink/?LinkId=81397).</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="72c00-112">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="72c00-112">For More Information</span></span>  
 [<span data-ttu-id="72c00-113">Administrar la tabla suspect_pages &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="72c00-113">Manage the suspect_pages Table &#40;SQL Server&#41;</span></span>](../backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  
