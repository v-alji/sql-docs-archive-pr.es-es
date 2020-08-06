---
title: Seleccionar tablas y vistas de origen (Asistente para importación y exportación de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.selectsourcetablesandviews.f1
ms.assetid: f60e1a19-2ea6-403c-89ab-3e60ac533ea0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e18f9f34db7965033d4e1e62964060a26404a45e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674913"
---
# <a name="select-source-tables-and-views-sql-server-import-and-export-wizard"></a><span data-ttu-id="caa55-102">Seleccionar tablas y vistas de origen (Asistente para importación y exportación de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="caa55-102">Select Source Tables and Views (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="caa55-103">Use la página **seleccionar tablas y vistas de origen** para especificar las tablas y vistas que se van a copiar del origen de datos al destino.</span><span class="sxs-lookup"><span data-stu-id="caa55-103">Use the **Select Source Tables and Views** page to specify the tables and views to be copied from the data source to the destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="caa55-104">No es necesario copiar todas las columnas en una tabla al seleccionar la opción de copia de tabla.</span><span class="sxs-lookup"><span data-stu-id="caa55-104">You do not have to copy all the columns in a table when you select the Table Copy option.</span></span> <span data-ttu-id="caa55-105">Después de seleccionar una tabla de destino, haga clic en Editar asignaciones para mostrar el cuadro de diálogo **asignaciones de columnas** .</span><span class="sxs-lookup"><span data-stu-id="caa55-105">After selecting a destination table, click Edit Mappings to display the **Column Mappings** dialog box.</span></span> <span data-ttu-id="caa55-106">Seleccione **\<ignore>** en la columna **destino** del cuadro de diálogo **asignaciones de columnas** para las columnas que desea omitir.</span><span class="sxs-lookup"><span data-stu-id="caa55-106">Select **\<ignore>** in the **Destination** column of the **Column Mappings** dialog box for columns that you want to skip.</span></span>  
  
 <span data-ttu-id="caa55-107">Para obtener más información acerca de este asistente, vea [Asistente para importación y exportación de SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="caa55-107">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="caa55-108">Para obtener información sobre las opciones para iniciar el asistente y sobre los permisos necesarios para ejecutar el asistente correctamente, vea [ejecutar el Asistente para importación y exportación de SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="caa55-108">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="caa55-109">La finalidad del Asistente para importación y exportación de SQL Server es copiar datos desde un origen a un destino.</span><span class="sxs-lookup"><span data-stu-id="caa55-109">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="caa55-110">El asistente también puede crear una base de datos y tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="caa55-110">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="caa55-111">Sin embargo, si tiene que copiar diversas bases de datos o tablas, u otros tipos de objetos de bases de datos, debe utilizar el Asistente para copiar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="caa55-111">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="caa55-112">Para más información, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="caa55-112">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="caa55-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="caa55-113">Options</span></span>  
  
### <a name="tables-and-views-list"></a><span data-ttu-id="caa55-114">Lista de tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="caa55-114">Tables and views List</span></span>  
 <span data-ttu-id="caa55-115">**Origen**</span><span class="sxs-lookup"><span data-stu-id="caa55-115">**Source**</span></span>  
 <span data-ttu-id="caa55-116">Utilice las casillas para seleccionar en la lista las tablas y vistas disponibles que deben copiarse en el destino.</span><span class="sxs-lookup"><span data-stu-id="caa55-116">Using the check boxes, select from the list of available tables and views to copy to the destination.</span></span> <span data-ttu-id="caa55-117">Si selecciona una tabla o una vista de origen y no realiza ninguna otra acción, copiará el esquema y los datos del origen sin cambios.</span><span class="sxs-lookup"><span data-stu-id="caa55-117">If you select a source table or view and perform no other action, the schema and data from the source are copied without changes.</span></span>  
  
 <span data-ttu-id="caa55-118">**Destino**</span><span class="sxs-lookup"><span data-stu-id="caa55-118">**Destination**</span></span>  
 <span data-ttu-id="caa55-119">Seleccione una tabla de destino de la lista para cada tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="caa55-119">Select a destination table from the list for each source table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="caa55-120">Si interrumpe el asistente en este punto para crear una tabla de destino en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] o con otra herramienta, la nueva tabla no será visible de forma inmediata en la lista de tablas de destino disponibles.</span><span class="sxs-lookup"><span data-stu-id="caa55-120">If you pause at this point in the wizard to create a destination table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] or another tool, the new table is not immediately visible in the list of available destination tables.</span></span> <span data-ttu-id="caa55-121">Para actualizar la lista de tablas de destino, retroceda dos páginas hasta la página **elegir un destino** , vuelva a seleccionar la base de datos de destino y, a continuación, vuelva a avanzar a la **selección de tablas y vistas de origen**.</span><span class="sxs-lookup"><span data-stu-id="caa55-121">To refresh the list of destination tables, step back two pages to the **Choose a Destination** page, re-select the destination database, then step forward again to the **Select Source Tables and Views**.</span></span>  
  
### <a name="other-options"></a><span data-ttu-id="caa55-122">Otras opciones</span><span class="sxs-lookup"><span data-stu-id="caa55-122">Other Options</span></span>  
 <span data-ttu-id="caa55-123">**Editar asignaciones**</span><span class="sxs-lookup"><span data-stu-id="caa55-123">**Edit mappings**</span></span>  
 <span data-ttu-id="caa55-124">Utilice el cuadro de diálogo **asignaciones de columnas** para especificar las columnas de destino que van a recibir los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="caa55-124">Use the **Column Mappings** dialog box to specify destination columns to receive the source data.</span></span> <span data-ttu-id="caa55-125">Puede copiar solo un subconjunto de columnas seleccionando \<ignore> en la columna **destino** del cuadro de diálogo **asignaciones de columnas** para las columnas que desea omitir.</span><span class="sxs-lookup"><span data-stu-id="caa55-125">You can copy only a subset of columns by selecting \<ignore> in the **Destination** column of the **Column Mappings** dialog box for columns that you want to skip.</span></span>  
  
 <span data-ttu-id="caa55-126">**Versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="caa55-126">**Preview**</span></span>  
 <span data-ttu-id="caa55-127">Obtenga una vista previa de los datos de origen en el cuadro de diálogo **vista previa** de los datos para comprobarlo antes de realizar la importación o exportación.</span><span class="sxs-lookup"><span data-stu-id="caa55-127">Preview source data in the **Preview Data** dialog box to verify it before performing the import or export.</span></span> <span data-ttu-id="caa55-128">El cuadro de diálogo **vista previa** de los datos muestra hasta 200 filas de datos.</span><span class="sxs-lookup"><span data-stu-id="caa55-128">The **Preview Data** dialog box displays up to 200 rows of data.</span></span>  
  
 <span data-ttu-id="caa55-129">Después de ofrecer una vista previa de los datos, puede que desee cambiar las opciones que ha seleccionado para el origen y el destino.</span><span class="sxs-lookup"><span data-stu-id="caa55-129">After previewing the data, you might want to change the options that you have selected for the data source and destination.</span></span> <span data-ttu-id="caa55-130">Para realizar estas modificaciones, en la página **Seleccionar tablas y vistas de origen** , haga clic en **Atrás** para volver a las páginas anteriores en las que puede cambiar sus selecciones.</span><span class="sxs-lookup"><span data-stu-id="caa55-130">To make these changes, on the **Select Source Tables and Views** page, click **Back** to return to previous pages where you can change your selections.</span></span>  
  
  
