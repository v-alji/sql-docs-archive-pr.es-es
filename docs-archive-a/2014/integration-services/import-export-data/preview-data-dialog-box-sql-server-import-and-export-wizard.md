---
title: Cuadro de diálogo Vista previa de los datos (Asistente para importación y exportación de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.previewdata.f1
ms.assetid: 423ac26a-ba02-4fdf-88b4-07995fe4a97e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 17debc001d8ba7826fe845c006e944e5a3dc87a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674922"
---
# <a name="preview-data-dialog-box-sql-server-import-and-export-wizard"></a><span data-ttu-id="5c9cf-102">Cuadro de diálogo Vista previa de los datos (Asistente para importación y exportación de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5c9cf-102">Preview Data Dialog Box (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="5c9cf-103">Utilice el cuadro de diálogo **vista previa** de los datos para ver la consulta que el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Asistente para importación y exportación de enviará al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5c9cf-103">Use the **Preview Data** dialog box to see the query that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard will send to the data source.</span></span> <span data-ttu-id="5c9cf-104">También puede usar este cuadro de diálogo para obtener una vista previa de hasta 200 filas de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5c9cf-104">You can also use this dialog box to preview up to 200 rows of sample data.</span></span>  
  
 <span data-ttu-id="5c9cf-105">Para obtener más información sobre el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Asistente para importación y exportación de, vea [SQL Server Asistente para importación y exportación](import-and-export-data-with-the-sql-server-import-and-export-wizard.md)de.</span><span class="sxs-lookup"><span data-stu-id="5c9cf-105">To learn more about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="5c9cf-106">Para obtener información sobre las opciones para iniciar el asistente y sobre los permisos necesarios para ejecutar el asistente correctamente, vea [ejecutar el Asistente para importación y exportación de SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5c9cf-106">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="5c9cf-107">La finalidad del Asistente para importación y exportación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es copiar datos desde un origen a un destino.</span><span class="sxs-lookup"><span data-stu-id="5c9cf-107">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="5c9cf-108">El asistente también puede crear una base de datos y tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="5c9cf-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="5c9cf-109">Sin embargo, si tiene que copiar diversas bases de datos o tablas, u otros tipos de objetos de bases de datos, debe utilizar el Asistente para copiar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="5c9cf-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="5c9cf-110">Para más información, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5c9cf-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
 <span data-ttu-id="5c9cf-111">**Para abrir el cuadro de diálogo Vista previa de los datos**</span><span class="sxs-lookup"><span data-stu-id="5c9cf-111">**To open the Preview Data dialog box**</span></span>  
  
-   <span data-ttu-id="5c9cf-112">En la página **seleccionar tablas y vistas de origen** del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Asistente para importación y exportación de, haga clic en **vista previa**.</span><span class="sxs-lookup"><span data-stu-id="5c9cf-112">On the **Select Source Tables and Views** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, click **Preview**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5c9cf-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="5c9cf-113">Options</span></span>  
 <span data-ttu-id="5c9cf-114">**Origen**</span><span class="sxs-lookup"><span data-stu-id="5c9cf-114">**Source**</span></span>  
 <span data-ttu-id="5c9cf-115">Muestra la consulta que el asistente enviará al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5c9cf-115">Displays the query that the wizard will send to the data source.</span></span>  
  
 <span data-ttu-id="5c9cf-116">**Cuadricula de datos de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="5c9cf-116">**Sample data grid**</span></span>  
 <span data-ttu-id="5c9cf-117">Muestra hasta 200 filas de datos de ejemplo devueltos por la consulta.</span><span class="sxs-lookup"><span data-stu-id="5c9cf-117">Displays up to 200 rows of sample data that the query returned.</span></span>  
  
  
