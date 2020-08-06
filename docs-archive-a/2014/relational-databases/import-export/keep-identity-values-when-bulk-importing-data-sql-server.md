---
title: Mantenimiento de valores de identidad al importar datos de forma masiva (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- identity values [SQL Server], bulk imports
- data formats [SQL Server], identity values
- bulk importing [SQL Server], identity values
ms.assetid: 45894a3f-2d8a-4edd-9568-afa7d0d3061f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07f6714f27f60afda91134034509ff439d92f071
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675370"
---
# <a name="keep-identity-values-when-bulk-importing-data-sql-server"></a><span data-ttu-id="4c269-102">Mantener valores de identidad al importar datos de forma masiva (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4c269-102">Keep Identity Values When Bulk Importing Data (SQL Server)</span></span>
  <span data-ttu-id="4c269-103">Los archivos de datos que contienen valores de identidad pueden importarse de forma masiva en una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c269-103">Data files that contain identity values can be bulk imported into an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4c269-104">De manera predeterminada, los valores de la columna de identidad del archivo de datos que se importa se omiten y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asigna automáticamente valores únicos.</span><span class="sxs-lookup"><span data-stu-id="4c269-104">By default, the values for the identity column in the data file that is imported are ignored and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns unique values automatically.</span></span> <span data-ttu-id="4c269-105">Los valores únicos se basan en los valores de inicialización y de incremento especificados durante la creación de la tabla.</span><span class="sxs-lookup"><span data-stu-id="4c269-105">The unique values are based on the seed and increment values that are specified during table creation.</span></span>  
  
 <span data-ttu-id="4c269-106">Si el archivo de datos no contiene valores para la columna de identificadores de la tabla, use el archivo de formato para especificar que se debe omitir esta columna al importar los datos.</span><span class="sxs-lookup"><span data-stu-id="4c269-106">If the data file does not contain values for the identifier column in the table, use a format file to specify that the identifier column in the table should be skipped when importing data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4c269-107">asignará automáticamente valores exclusivos para la columna.</span><span class="sxs-lookup"><span data-stu-id="4c269-107">assigns unique values for the column automatically.</span></span>  
  
 <span data-ttu-id="4c269-108">Para impedir que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asigne valores de identidad al importar de forma masiva filas de datos en una tabla, utilice el calificador de comando adecuado para mantener la identidad.</span><span class="sxs-lookup"><span data-stu-id="4c269-108">To prevent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from assigning identity values while bulk importing data rows into a table, use the appropriate keep-identity command qualifier.</span></span> <span data-ttu-id="4c269-109">Al especificar un calificador para mantener la identidad, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utiliza los valores de identidad del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="4c269-109">When you specify a keep-identity qualifier, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the identity values in the data file.</span></span> <span data-ttu-id="4c269-110">Estos calificadores son:</span><span class="sxs-lookup"><span data-stu-id="4c269-110">These qualifiers are as follows:</span></span>  
  
|<span data-ttu-id="4c269-111">Get-Help</span><span class="sxs-lookup"><span data-stu-id="4c269-111">Command</span></span>|<span data-ttu-id="4c269-112">Calificador para mantener la identidad</span><span class="sxs-lookup"><span data-stu-id="4c269-112">Keep-identity qualifier</span></span>|<span data-ttu-id="4c269-113">Tipo de calificador</span><span class="sxs-lookup"><span data-stu-id="4c269-113">Qualifier type</span></span>|  
|-------------|------------------------------|--------------------|  
|`bcp`|<span data-ttu-id="4c269-114">**-E**</span><span class="sxs-lookup"><span data-stu-id="4c269-114">**-E**</span></span>|<span data-ttu-id="4c269-115">Switch</span><span class="sxs-lookup"><span data-stu-id="4c269-115">Switch</span></span>|  
|<span data-ttu-id="4c269-116">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="4c269-116">BULK INSERT</span></span>|<span data-ttu-id="4c269-117">KEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="4c269-117">KEEPIDENTITY</span></span>|<span data-ttu-id="4c269-118">Argumento</span><span class="sxs-lookup"><span data-stu-id="4c269-118">Argument</span></span>|  
|<span data-ttu-id="4c269-119">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="4c269-119">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="4c269-120">KEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="4c269-120">KEEPIDENTITY</span></span>|<span data-ttu-id="4c269-121">Sugerencia de tabla</span><span class="sxs-lookup"><span data-stu-id="4c269-121">Table hint</span></span>|  
  
 <span data-ttu-id="4c269-122">Para obtener más información, vea [bcp (utilidad)](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) y [Sugerencias de tabla &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table).</span><span class="sxs-lookup"><span data-stu-id="4c269-122">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), and [Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c269-123">Para crear un número que se incremente automáticamente y que se pueda usar en varias tablas, o que se pueda llamar desde las aplicaciones sin hacer referencia a ninguna tabla, vea [Números de secuencia](../sequence-numbers/sequence-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="4c269-123">To create an automatically incrementing number that can be used in multiple tables or that can be called from applications without referencing any table, see [Sequence Numbers](../sequence-numbers/sequence-numbers.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4c269-124">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4c269-124">Examples</span></span>  
 <span data-ttu-id="4c269-125">Los ejemplos de este tema importan datos de forma masiva mediante INSERT... Seleccione \* FROM OPENROWSET (BULK...) y mantenga los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="4c269-125">The examples in this topic bulk import data using INSERT ... SELECT \* FROM OPENROWSET(BULK...) and keeping default values.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="4c269-126">Tabla de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c269-126">Sample Table</span></span>  
 <span data-ttu-id="4c269-127">En ejemplos de importación en bloque, es necesario crear una tabla denominada **myTestKeepNulls** en la base de datos de ejemplo **AdventureWorks** en el esquema **dbo**.</span><span class="sxs-lookup"><span data-stu-id="4c269-127">The bulk-import examples require that a table named **myTestKeepNulls** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="4c269-128">Para crear esta tabla</span><span class="sxs-lookup"><span data-stu-id="4c269-128">To create this table.</span></span> <span data-ttu-id="4c269-129">en el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], ejecute:</span><span class="sxs-lookup"><span data-stu-id="4c269-129">in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
SELECT * INTO HumanResources.myDepartment   
   FROM HumanResources.Department  
      WHERE 1=0;  
GO  
SELECT * FROM HumanResources.myDepartment;  
```  
  
 <span data-ttu-id="4c269-130">La tabla **Department** en la que se basa `myDepartment` tiene IDENTITY_INSERT establecido en OFF.</span><span class="sxs-lookup"><span data-stu-id="4c269-130">The **Department** table on which `myDepartment` is based has IDENTITY_INSERT is set to OFF.</span></span> <span data-ttu-id="4c269-131">Por tanto, para importar datos en una columna de identidad, debe especificar KEEPIDENTITY o **-E**.</span><span class="sxs-lookup"><span data-stu-id="4c269-131">Therefore, to import data into an identity column you must specify KEEPIDENTITY or **-E**.</span></span>  
  
### <a name="sample-data-file"></a><span data-ttu-id="4c269-132">Archivo de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c269-132">Sample Data File</span></span>  
 <span data-ttu-id="4c269-133">El archivo de datos usado en los ejemplos de importación masiva contiene datos exportados de forma masiva desde la tabla `HumanResources.Department` en formato nativo.</span><span class="sxs-lookup"><span data-stu-id="4c269-133">The data file used in the bulk-import examples contains data bulk exported from the `HumanResources.Department` table in native format.</span></span> <span data-ttu-id="4c269-134">Para crear el archivo de datos, en el símbolo del sistema de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, escriba:</span><span class="sxs-lookup"><span data-stu-id="4c269-134">To create the data file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.Department out myDepartment-n.Dat -n -T  
```  
  
### <a name="sample-format-file"></a><span data-ttu-id="4c269-135">Archivo de formato de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c269-135">Sample Format File</span></span>  
 <span data-ttu-id="4c269-136">En este ejemplo de importación masiva se usa un archivo de formato XML, `myDepartment-f-x-n.Xml`, que usa formatos de datos nativos.</span><span class="sxs-lookup"><span data-stu-id="4c269-136">This bulk-import examples use an XML format file, `myDepartment-f-x-n.Xml`, which uses native data formats.</span></span> <span data-ttu-id="4c269-137">En este ejemplo se usa `bcp` para generar este archivo de formato desde la tabla `HumanResources.Department` de la base de datos `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="4c269-137">This example uses `bcp` to create to generate this format file from the `HumanResources.Department` table of the `AdventureWorks` database.</span></span> <span data-ttu-id="4c269-138">En el símbolo del sistema de Windows, escriba:</span><span class="sxs-lookup"><span data-stu-id="4c269-138">At the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.Department format nul -n -x -f myDepartment-f-n-x.Xml -T  
```  
  
 <span data-ttu-id="4c269-139">Para obtener más información sobre cómo crear un archivo de formato, vea [Crear un archivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4c269-139">For more information about creating a format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
### <a name="a-using-bcp-and-keeping-identity-values"></a><span data-ttu-id="4c269-140">A.</span><span class="sxs-lookup"><span data-stu-id="4c269-140">A.</span></span> <span data-ttu-id="4c269-141">Usar bcp y mantener valores de identidad</span><span class="sxs-lookup"><span data-stu-id="4c269-141">Using bcp and Keeping Identity Values</span></span>  
 <span data-ttu-id="4c269-142">En el siguiente ejemplo se muestra cómo mantener valores de identidad al usar `bcp` para importar datos de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="4c269-142">The following example demonstrates how to keep identity values when using `bcp` to bulk import data.</span></span> <span data-ttu-id="4c269-143">El comando `bcp` usa el archivo de formato, `myDepartment-f-n-x.Xml`, y contiene los siguientes modificadores:</span><span class="sxs-lookup"><span data-stu-id="4c269-143">The `bcp` command uses the format file, `myDepartment-f-n-x.Xml`, and contains the following switches:</span></span>  
  
|<span data-ttu-id="4c269-144">Calificadores</span><span class="sxs-lookup"><span data-stu-id="4c269-144">Qualifiers</span></span>|<span data-ttu-id="4c269-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c269-145">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="4c269-146">**-E**</span><span class="sxs-lookup"><span data-stu-id="4c269-146">**-E**</span></span>|<span data-ttu-id="4c269-147">Especifica el valor o valores de identidad del archivo de datos que se van a usar en la columna de identidad.</span><span class="sxs-lookup"><span data-stu-id="4c269-147">Specifies that identity value or values in the data file are to be used for the identity column.</span></span>|  
|<span data-ttu-id="4c269-148">**-T**</span><span class="sxs-lookup"><span data-stu-id="4c269-148">**-T**</span></span>|<span data-ttu-id="4c269-149">Especifica que la `bcp` utilidad se conecta a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con una conexión de confianza.</span><span class="sxs-lookup"><span data-stu-id="4c269-149">Specifies that the `bcp` utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection.</span></span>|  
  
 <span data-ttu-id="4c269-150">En el símbolo del sistema de Windows, escriba:</span><span class="sxs-lookup"><span data-stu-id="4c269-150">At the Windows command prompt, enter.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myDepartment in C:\myDepartment-n.Dat -f C:\myDepartment-f-n-x.Xml -E -T  
  
```  
  
### <a name="b-using-bulk-insert-and-keeping-identity-values"></a><span data-ttu-id="4c269-151">B.</span><span class="sxs-lookup"><span data-stu-id="4c269-151">B.</span></span> <span data-ttu-id="4c269-152">Usar BULK INSERT y mantener valores de identidad</span><span class="sxs-lookup"><span data-stu-id="4c269-152">Using BULK INSERT and Keeping Identity Values</span></span>  
 <span data-ttu-id="4c269-153">En el siguiente ejemplo se utiliza BULK INSERT para realizar una importación masiva de datos desde el archivo `myDepartment-c.Dat` en la tabla `AdventureWorks.HumanResources.myDepartment` .</span><span class="sxs-lookup"><span data-stu-id="4c269-153">The following example uses BULK INSERT to bulk import data from the `myDepartment-c.Dat` file into the `AdventureWorks.HumanResources.myDepartment` table.</span></span> <span data-ttu-id="4c269-154">La instrucción utiliza el archivo de formato `myDepartment-f-n-x.Xml` e incluye la opción KEEPIDENTITY para que se mantengan todos los valores de identidad del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="4c269-154">The statement uses the `myDepartment-f-n-x.Xml` format file and includes the KEEPIDENTITY option to ensure that any identity values in the data file are retained.</span></span>  
  
 <span data-ttu-id="4c269-155">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], ejecute:</span><span class="sxs-lookup"><span data-stu-id="4c269-155">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
DELETE HumanResources.myDepartment;  
GO  
BULK INSERT HumanResources.myDepartment  
   FROM 'C:\myDepartment-n.Dat'  
   WITH (  
      KEEPIDENTITY,  
      FORMATFILE='C:\myDepartment-f-n-x.Xml'  
   );  
GO  
SELECT * FROM HumanResources.myDepartment;  
  
```  
  
### <a name="c-using-openrowset-and-keeping-identity-values"></a><span data-ttu-id="4c269-156">C.</span><span class="sxs-lookup"><span data-stu-id="4c269-156">C.</span></span> <span data-ttu-id="4c269-157">Usar OPENROWSET y mantener valores de identidad</span><span class="sxs-lookup"><span data-stu-id="4c269-157">Using OPENROWSET and Keeping Identity Values</span></span>  
 <span data-ttu-id="4c269-158">En el siguiente ejemplo se utiliza el proveedor de conjuntos de filas BULK, OPENROWSET, para realizar una importación masiva de datos desde el archivo `myDepartment-c.Dat` en la tabla `AdventureWorks.HumanResources.myDepartment` .</span><span class="sxs-lookup"><span data-stu-id="4c269-158">The following example uses the OPENROWSET bulk rowset provider to bulk import data from the `myDepartment-c.Dat` file into the `AdventureWorks.HumanResources.myDepartment` table.</span></span> <span data-ttu-id="4c269-159">La instrucción utiliza el archivo de formato `myDepartment-f-n-x.Xml` e incluye la sugerencia KEEPIDENTITY para que se mantengan todos los valores de identidad del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="4c269-159">The statement uses the `myDepartment-f-n-x.Xml` format file and includes the KEEPIDENTITY hint to ensure that any identity values in the data file are retained.</span></span>  
  
 <span data-ttu-id="4c269-160">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], ejecute:</span><span class="sxs-lookup"><span data-stu-id="4c269-160">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
DELETE HumanResources.myDepartment;  
GO  
  
INSERT INTO HumanResources.myDepartment  
   with (KEEPIDENTITY)  
   (DepartmentID, Name, GroupName, ModifiedDate)  
   SELECT *  
      FROM  OPENROWSET(BULK 'C:\myDepartment-n.Dat',  
      FORMATFILE='C:\myDepartment-f-n-x.Xml') as t1;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4c269-161">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="4c269-161">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4c269-162">Mantener valores NULL o usar valores predeterminados durante la importación en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c269-162">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
-   [<span data-ttu-id="4c269-163">Preparar los datos para exportar o importar en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c269-163">Prepare Data for Bulk Export or Import &#40;SQL Server&#41;</span></span>](prepare-data-for-bulk-export-or-import-sql-server.md)  
  
 <span data-ttu-id="4c269-164">**Para usar un archivo de formato**</span><span class="sxs-lookup"><span data-stu-id="4c269-164">**To use a format file**</span></span>  
  
-   [<span data-ttu-id="4c269-165">Crear un archivo de formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c269-165">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="4c269-166">Usar un archivo de formato para importar datos en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c269-166">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="4c269-167">Usar un archivo de formato para asignar columnas de tabla a campos de un archivo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c269-167">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
-   [<span data-ttu-id="4c269-168">Usar un archivo de formato para omitir un campo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c269-168">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="4c269-169">Usar un archivo de formato para omitir una columna de tabla &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c269-169">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 <span data-ttu-id="4c269-170">**Para usar formatos de datos para la importación o exportación masivas**</span><span class="sxs-lookup"><span data-stu-id="4c269-170">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="4c269-171">Importar datos con formato nativo y de caracteres de versiones anteriores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4c269-171">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="4c269-172">Usar el formato de caracteres para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c269-172">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="4c269-173">Usar el formato nativo para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c269-173">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="4c269-174">Usar el formato de caracteres Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c269-174">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="4c269-175">Usar el formato nativo Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c269-175">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 <span data-ttu-id="4c269-176">**Para especificar formatos de datos por razones de compatibilidad cuando se usa bcp**</span><span class="sxs-lookup"><span data-stu-id="4c269-176">**To specify data formats for compatibility when using bcp**</span></span>  
  
1.  [<span data-ttu-id="4c269-177">Especificar terminadores de campo y de fila &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c269-177">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
2.  [<span data-ttu-id="4c269-178">Especificar la longitud de prefijo en los archivos de datos mediante bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c269-178">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
3.  [<span data-ttu-id="4c269-179">Especificar el tipo de almacenamiento en archivo mediante bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c269-179">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="4c269-180">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c269-180">See Also</span></span>  
 <span data-ttu-id="4c269-181">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c269-181">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="4c269-182">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="4c269-182">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="4c269-183">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c269-183">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="4c269-184">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c269-184">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="4c269-185">Sugerencias de tabla &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4c269-185">Table Hints &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/hints-transact-sql-table)  
  
  
