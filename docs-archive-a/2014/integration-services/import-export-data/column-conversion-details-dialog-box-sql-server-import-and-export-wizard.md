---
title: Cuadro de diálogo Detalles de conversión de columna (Asistente para importación y exportación de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.issuedetails.f1
ms.assetid: e2d00a39-dfbd-4821-a4d8-a5bd1164ed4d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9207e76191060c56acad37db734827579a83aae0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674939"
---
# <a name="column-conversion-details-dialog-box-sql-server-import-and-export-wizard"></a><span data-ttu-id="b4322-102">Cuadro de diálogo Detalles de conversión de columna (Asistente para importación y exportación de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b4322-102">Column Conversion Details Dialog Box (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="b4322-103">Utilice el cuadro de diálogo **detalles de conversión de columna** para revisar información de conversión detallada sobre una columna individual.</span><span class="sxs-lookup"><span data-stu-id="b4322-103">Use the **Column Conversion Details** dialog box to review detailed conversion information about an individual column.</span></span> <span data-ttu-id="b4322-104">Esta información de conversión contiene el tipo de datos de la columna en el origen y el destino, y la conversión que el asistente realizará.</span><span class="sxs-lookup"><span data-stu-id="b4322-104">This conversion information contains the column's data type at the source and the destination, and the conversion that the wizard will perform.</span></span> <span data-ttu-id="b4322-105">En esta página también se enumeran los archivos de asignación de tipos de datos que el asistente utiliza para determinar las conversiones de tipos de datos que se requieren.</span><span class="sxs-lookup"><span data-stu-id="b4322-105">This page also lists the data type mapping files that the wizard uses to determine the data type conversions that are required.</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="b4322-106">instala estos archivos de asignación de tipos de datos durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="b4322-106">installs these data type mapping files during setup.</span></span>  
  
 <span data-ttu-id="b4322-107">**Para abrir el cuadro de diálogo Detalles de conversión de columna**</span><span class="sxs-lookup"><span data-stu-id="b4322-107">**To open the Column Conversion Details dialog box**</span></span>  
  
1.  <span data-ttu-id="b4322-108">En la página **revisar problemas de tipos de datos** del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Asistente para importación y exportación de, en la lista **tabla** , seleccione una tabla.</span><span class="sxs-lookup"><span data-stu-id="b4322-108">On the **Review Data Type Issues** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, in the **Table** list, select a table.</span></span>  
  
2.  <span data-ttu-id="b4322-109">En la lista **asignación de tipos de datos** , haga doble clic en la fila que contiene la columna para la que desea ver los detalles de la conversión.</span><span class="sxs-lookup"><span data-stu-id="b4322-109">In the **Data type mapping** list, double-click the row that contains the column for which you want to view conversion details.</span></span>  
  
 <span data-ttu-id="b4322-110">Para obtener más información sobre el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Asistente para importación y exportación de, vea [SQL Server Asistente para importación y exportación](import-and-export-data-with-the-sql-server-import-and-export-wizard.md)de.</span><span class="sxs-lookup"><span data-stu-id="b4322-110">To learn more about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="b4322-111">Para obtener información sobre las opciones para iniciar el asistente y sobre los permisos necesarios para ejecutar el asistente correctamente, vea [ejecutar el Asistente para importación y exportación de SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="b4322-111">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="b4322-112">La finalidad del Asistente para importación y exportación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es copiar datos desde un origen a un destino.</span><span class="sxs-lookup"><span data-stu-id="b4322-112">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="b4322-113">El asistente también puede crear una base de datos y tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="b4322-113">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="b4322-114">Sin embargo, si tiene que copiar diversas bases de datos o tablas, u otros tipos de objetos de bases de datos, debe utilizar el Asistente para copiar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="b4322-114">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="b4322-115">Para más información, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="b4322-115">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
  
