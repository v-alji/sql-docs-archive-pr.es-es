---
title: Archivos de formato XML (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- format files [SQL Server], XML format files
- bulk importing [SQL Server], format files
- XML format files [SQL Server]
ms.assetid: 69024aad-eeea-4187-8fea-b49bc2359849
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7cc1e8de30fa582898ef8516b9767dec14c4fa81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675871"
---
# <a name="xml-format-files-sql-server"></a><span data-ttu-id="e8d1b-102">XML, archivos de formato (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e8d1b-102">XML Format Files (SQL Server)</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="e8d1b-103">proporciona un esquema XML que define la sintaxis para escribir *archivos de formato XML* que se usarán para la importación masiva de datos en una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e8d1b-103">provides an XML schema that defines syntax for writing *XML format files* to use for bulk importing data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="e8d1b-104">Los archivos de formato XML deben adherirse a este esquema, que se define en el lenguaje de definición de esquemas XML (XSDL).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-104">XML format files must adhere to this schema, which is defined in the XML Schema Definition Language (XSDL).</span></span> <span data-ttu-id="e8d1b-105">Los archivos con formato XML solamente se admiten cuando se instalan herramientas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-105">XML format files are only supported when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tools are installed together with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 <span data-ttu-id="e8d1b-106">Puede usar un archivo de formato XML con un comando **bcp**, una instrucción BULK INSERT o una instrucción INSERT... Instrucción SELECT \* FROM OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-106">You can use an XML format file with a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="e8d1b-107">El comando **bcp** permite generar automáticamente un archivo de formato XML para una tabla; para más información, consulte [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-107">The **bcp** command allows you to automatically generate an XML format file for a table; for more information, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8d1b-108">Se admiten dos tipos de archivos de formato para la importación y exportación masivas: *archivos de formato no XML* y *archivos de formato XML*.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-108">Two types of format files are supported for bulk exporting and importing: *non-XML format files* and *XML format files*.</span></span> <span data-ttu-id="e8d1b-109">Los archivos de formato XML proporcionan una alternativa flexible y eficaz a los archivos de formato no XML.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-109">XML format files provide a flexible and powerful alternative to non-XML format files.</span></span> <span data-ttu-id="e8d1b-110">Para obtener información sobre los archivos de formato no XML, vea [Archivos de formato no XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-110">For information about non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  

  
##  <a name="benefits-of-xml-format-files"></a><a name="BenefitsOfXmlFFs"></a> <span data-ttu-id="e8d1b-111">Ventajas de los archivos de formato XML</span><span class="sxs-lookup"><span data-stu-id="e8d1b-111">Benefits of XML Format Files</span></span>  
  
-   <span data-ttu-id="e8d1b-112">Los archivos de formato XML son autodescriptivos, lo que facilita su lectura, creación y ampliación.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-112">XML format files are self-describing, making them easy to read, create, and extend.</span></span> <span data-ttu-id="e8d1b-113">Los usuarios pueden leerlos, lo que facilita la comprensión del modo en que se interpretan los datos durante las operaciones masivas.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-113">They are human readable, making it easy to understand how data is interpreted during bulk operations.</span></span>  
  
-   <span data-ttu-id="e8d1b-114">Los archivos de formato XML contienen los tipos de datos de las columnas de destino.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-114">XML format files contain the data types of target columns.</span></span>  <span data-ttu-id="e8d1b-115">La codificación XML describe claramente los tipos de datos y elementos de datos del archivo de datos, así como la asignación entre los elementos de datos y las columnas de las tablas.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-115">The XML encoding clearly describes the data types and data elements of the data file and also the mapping between data elements and table columns.</span></span>  
  
     <span data-ttu-id="e8d1b-116">Esta característica habilita la separación entre la representación de los datos en el archivo de datos y el tipo de datos asociado a cada campo del archivo.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-116">This enables separation between how data is represented in the data file and what data type is associated with each field in the file.</span></span> <span data-ttu-id="e8d1b-117">Por ejemplo, si un archivo de datos contiene una representación de caracteres de los datos, se perderá el tipo de columna SQL correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-117">For example, if a data file contains a character representation of the data, the corresponding SQL column type is lost.</span></span>  
  
-   <span data-ttu-id="e8d1b-118">Un archivo de formato XML permite cargar un campo que contenga un único tipo de datos de objeto grande (LOB) desde un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-118">An XML format file allows for loading of a field that contains a single large object (LOB) data type from a data file.</span></span>  
  
-   <span data-ttu-id="e8d1b-119">Un archivo de formato XML puede mejorarse manteniendo su compatibilidad con sus versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-119">An XML format file can be enhanced yet remain compatible with its earlier versions.</span></span> <span data-ttu-id="e8d1b-120">Además, la claridad de la codificación XML facilita la creación de varios archivos de formato para un determinado archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-120">Furthermore, the clarity of XML encoding facilitates the creation of multiple format files for a given data file.</span></span> <span data-ttu-id="e8d1b-121">Esto es útil si tiene que asignar todos o algunos campos de datos a columnas de diferentes tablas o vistas.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-121">This is useful if you have to map all or some of the data fields to columns in different tables or views.</span></span>  
  
-   <span data-ttu-id="e8d1b-122">La sintaxis XML es independiente de la dirección de la operación; es decir, la sintaxis es la misma para exportaciones e importaciones masivas.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-122">The XML syntax is independent of the direction of the operation; that is, the syntax is the same for bulk export and bulk import.</span></span>  
  
-   <span data-ttu-id="e8d1b-123">Puede usar los archivos de formato XML para importar los datos de forma masiva en tablas o vistas sin particiones y para exportar los datos de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-123">You can use XML format files to bulk import data into tables or non-partitioned views and to bulk export data.</span></span>  
  
-   <span data-ttu-id="e8d1b-124">Para OPENROWSET(BULK…) la función que especifica una tabla de destino es opcional.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-124">For the OPENROWSET(BULK...) function specifying a target table is optional.</span></span> <span data-ttu-id="e8d1b-125">Esto se debe a que la función se basa en el archivo de formato XML para leer datos de un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-125">This is because the function relies on the XML format file to read data from a data file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8d1b-126">Es necesaria una tabla de destino con el comando **bcp** y la instrucción BULK INSERT, que usa las columnas de la tabla de destino para realizar la conversión de tipos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-126">A target table is necessary with the **bcp** command and the BULK INSERT statement, which uses the target table columns to do the type conversion.</span></span>  
  
##  <a name="structure-of-xml-format-files"></a><a name="StructureOfXmlFFs"></a> <span data-ttu-id="e8d1b-127">Estructura de los archivos de formato XML</span><span class="sxs-lookup"><span data-stu-id="e8d1b-127">Structure of XML Format Files</span></span>  
 <span data-ttu-id="e8d1b-128">Al igual que un archivo de formato no XML, un archivo de formato XML define el formato y la estructura de los campos de datos de un archivo de datos y asigna dichos campos a columnas de una sola tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-128">Like a non-XML format file, an XML format file defines the format and structure of the data fields in a data file and maps those data fields to columns in a single target table.</span></span>  
  
 <span data-ttu-id="e8d1b-129">Un archivo con formato XML posee dos componentes principales, \<RECORD> y \<ROW>:</span><span class="sxs-lookup"><span data-stu-id="e8d1b-129">An XML format file possesses two main components, \<RECORD> and \<ROW>:</span></span>  
  
-   <span data-ttu-id="e8d1b-130">\<RECORD> describe los datos tal y como se almacenan en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-130">\<RECORD> describes the data as it is stored in the data file.</span></span>  
  
     <span data-ttu-id="e8d1b-131">Cada elemento \<RECORD> contiene un conjunto de uno o más elementos \<FIELD>.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-131">Each \<RECORD> element contains a set of one or more \<FIELD> elements.</span></span> <span data-ttu-id="e8d1b-132">Dichos elementos corresponden a los campos del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-132">These elements correspond to fields in the data file.</span></span> <span data-ttu-id="e8d1b-133">La sintaxis básica es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8d1b-133">The basic syntax is as follows:</span></span>  
  
     \<RECORD>  
  
     <span data-ttu-id="e8d1b-134">\<FIELD .../> [ ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="e8d1b-134">\<FIELD .../> [ ...*n* ]</span></span>  
  
     \</RECORD>  
  
     <span data-ttu-id="e8d1b-135">Cada elemento \<FIELD> describe el contenido de un campo de datos concreto.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-135">Each \<FIELD> element describes the contents of a specific data field.</span></span> <span data-ttu-id="e8d1b-136">Un campo solo puede asignarse a una columna de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-136">A field can only be mapped to one column in the table.</span></span> <span data-ttu-id="e8d1b-137">No es necesario asignar todos los campos a columnas.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-137">Not all fields need to be mapped to columns.</span></span>  
  
     <span data-ttu-id="e8d1b-138">Un campo de un archivo de datos puede tener una longitud fija o variable, o bien terminar mediante un carácter.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-138">A field in a data file can be either of fixed/variable length or character terminated.</span></span> <span data-ttu-id="e8d1b-139">Un *valor de campo* puede representarse como: un carácter (mediante una representación de un solo byte), un carácter ancho (mediante la representación Unicode de dos bytes), un formato de base de datos nativo o un nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-139">A *field value* can be represented as: a character (using single-byte representation), a wide character (using Unicode two-byte representation), native database format, or a file name.</span></span> <span data-ttu-id="e8d1b-140">Si un valor de campo se representa como un nombre de archivo, éste apunta al archivo que contiene el valor de una columna BLOB en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-140">If a field value is represented as a file name, the file name points to the file that contains the value of a BLOB column in the target table.</span></span>  
  
-   <span data-ttu-id="e8d1b-141">\<ROW> describe el modo de construir filas de datos a partir de un archivo de datos cuando los datos del archivo se importan en una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8d1b-141">\<ROW> describes how to construct data rows from a data file when the data from the file is imported into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
     <span data-ttu-id="e8d1b-142">Un elemento \<ROW> contiene un conjunto de elementos \<COLUMN>.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-142">A \<ROW> element contains a set of \<COLUMN> elements.</span></span> <span data-ttu-id="e8d1b-143">Estos elementos corresponden a las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-143">These elements correspond to table columns.</span></span> <span data-ttu-id="e8d1b-144">La sintaxis básica es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8d1b-144">The basic syntax is as follows:</span></span>  
  
     \<ROW>  
  
     <span data-ttu-id="e8d1b-145">\<COLUMN .../> [ ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="e8d1b-145">\<COLUMN .../> [ ...*n* ]</span></span>  
  
     \</ROW>  
  
     <span data-ttu-id="e8d1b-146">Cada elemento \<COLUMN> solo se puede asignar a un campo del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-146">Each \<COLUMN> element can be mapped to only one field in the data file.</span></span> <span data-ttu-id="e8d1b-147">El orden de los elementos \<COLUMN> del elemento \<ROW> define el orden en el que la operación en bloque los devuelve.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-147">The order of the \<COLUMN> elements in the \<ROW> element defines the order in which they are returned by the bulk operation.</span></span> <span data-ttu-id="e8d1b-148">El archivo de formato XML asigna a cada elemento \<COLUMN> un nombre local que no tiene ninguna relación con la columna de la tabla de destino de una operación de importación en bloque.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-148">The XML format file assigns each \<COLUMN> element a local name that has no relationship to the column in the target table of a bulk import operation.</span></span>  
  
##  <a name="schema-syntax-for-xml-format-files"></a><a name="SchemaSyntax"></a> <span data-ttu-id="e8d1b-149">Sintaxis de esquema para archivos de formato XML</span><span class="sxs-lookup"><span data-stu-id="e8d1b-149">Schema Syntax for XML Format Files</span></span>  
 <span data-ttu-id="e8d1b-150">Esta sección contiene un resumen de los elementos y atributos del esquema XML para archivos de formato XML.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-150">This section contains a summary of the elements and attributes of the XML schema for XML format files.</span></span> <span data-ttu-id="e8d1b-151">La sintaxis de un archivo de formato es independiente de la dirección de la operación; es decir, la sintaxis es la misma para exportaciones e importaciones masivas.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-151">The syntax of a format file is independent of the direction of the operation; that is, the syntax is the same for bulk export and bulk import.</span></span> <span data-ttu-id="e8d1b-152">En esta sección también se describe cómo la importación en bloque usa los elementos \<ROW> y \<COLUMN>, y cómo colocar el valor xsi:type de un elemento en un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-152">This section also considers how bulk import uses the \<ROW> and \<COLUMN> elements and how to put the xsi:type value of an element into a data set.</span></span>  
  
 <span data-ttu-id="e8d1b-153">Para ver cómo la sintaxis corresponde a los archivos de formato XML reales, vea [Archivos de formato XML de ejemplo](#SampleXmlFFs), más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-153">To see how the syntax corresponds to actual XML format files, see [Sample XML Format Files](#SampleXmlFFs), later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8d1b-154">Puede modificar un archivo de formato de forma que le permita importar de forma masiva desde un archivo de datos en el que el número y/o el orden de los campos difieren del número y/o el orden de las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-154">You can modify a format file to let you bulk import from a data file in which the number and/or order of the fields differ from the number and/or order of table columns.</span></span> <span data-ttu-id="e8d1b-155">Para obtener más información, vea [Archivos de formato para importar o exportar datos &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-155">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
  
  
###  <a name="basic-syntax-of-the-xml-schema"></a><a name="BasicSyntax"></a> <span data-ttu-id="e8d1b-156">Sintaxis básica del esquema XML</span><span class="sxs-lookup"><span data-stu-id="e8d1b-156">Basic Syntax of the XML Schema</span></span>  
 <span data-ttu-id="e8d1b-157">Las instrucciones de esta sintaxis muestran solo los elementos (\<BCPFORMAT>, \<RECORD>, \<FIELD>, \<ROW> y \<COLUMN>), y sus atributos básicos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-157">This syntax statements show only the elements (\<BCPFORMAT>, \<RECORD>, \<FIELD>, \<ROW>, and \<COLUMN>) and their basic attributes.</span></span>  
  
 \<BCPFORMAT ...>  
  
 \<RECORD>  
  
 <span data-ttu-id="e8d1b-158">\<FIELD ID = "*fieldID*" xsi:type = "*fieldType*" [...]</span><span class="sxs-lookup"><span data-stu-id="e8d1b-158">\<FIELD ID = "*fieldID*" xsi:type = "*fieldType*" [...]</span></span>  
  
 />  
  
 \</RECORD>  
  
 \<ROW>  
  
 <span data-ttu-id="e8d1b-159">\<COLUMN SOURCE = "*fieldID*" NAME = "*columnName*" xsi:type = "*columnType*" [...]</span><span class="sxs-lookup"><span data-stu-id="e8d1b-159">\<COLUMN SOURCE = "*fieldID*" NAME = "*columnName*" xsi:type = "*columnType*" [...]</span></span>  
  
 />  
  
 \</ROW>  
  
 \</BCPFORMAT>  
  
> [!NOTE]  
>  <span data-ttu-id="e8d1b-160">Los atributos adicionales asociados al valor de xsi:type en un elemento \<FIELD> o \<COLUMN> se describen más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-160">Additional attributes that are associated with the value of the xsi:type in a \<FIELD> or \<COLUMN> element are described later in this topic.</span></span>  
  

  
####  <a name="schema-elements"></a><a name="SchemaElements"></a> <span data-ttu-id="e8d1b-161">Elementos de esquema</span><span class="sxs-lookup"><span data-stu-id="e8d1b-161">Schema Elements</span></span>  
 <span data-ttu-id="e8d1b-162">En esta sección se resume la finalidad de cada elemento que define el esquema XML para los archivos de formato XML.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-162">This section summarizes the purpose of each element that the XML schema defines for XML format files.</span></span> <span data-ttu-id="e8d1b-163">Los atributos se describen más adelante, en otras secciones de este tema.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-163">The attributes are described in separate sections later in this topic.</span></span>  
  
 \<BCPFORMAT>  
 <span data-ttu-id="e8d1b-164">Es el elemento de archivo de formato que define la estructura de los registros de un determinado archivo de datos y su correspondencia con las columnas de una fila de tabla en la tabla.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-164">Is the format-file element that defines the record structure of a given data file and its correspondence to the columns of a table row in the table.</span></span>  
  
 \<RECORD .../>  
 <span data-ttu-id="e8d1b-165">Define un elemento complejo que contiene uno o más elementos \<FIELD>.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-165">Defines a complex element containing one or more \<FIELD> elements.</span></span> <span data-ttu-id="e8d1b-166">El orden en que se declaran los campos en el archivo de formato es el orden en que estos campos aparecen en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-166">The order in which the fields are declared in the format file is the order in which those fields appear in the data file.</span></span>  
  
 \<FIELD .../>  
 <span data-ttu-id="e8d1b-167">Define un campo del archivo de datos que contiene datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-167">Defines a field in data file, which contains data.</span></span>  
  
 <span data-ttu-id="e8d1b-168">Los atributos de este elemento se tratan en la sección [Atributos del elemento \<FIELD>](#AttrOfFieldElement) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-168">The attributes of this element are discussed in [Attributes of the \<FIELD> Element](#AttrOfFieldElement), later in this topic.</span></span>  
  
 \<ROW .../>  
 <span data-ttu-id="e8d1b-169">Define un elemento complejo que contiene uno o más elementos \<COLUMN>.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-169">Defines a complex element containing one or more \<COLUMN> elements.</span></span> <span data-ttu-id="e8d1b-170">El orden de los elementos \<COLUMN> es independiente del de los elementos \<FIELD> de una definición RECORD.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-170">The order of the \<COLUMN> elements is independent of the order of \<FIELD> elements in a RECORD definition.</span></span> <span data-ttu-id="e8d1b-171">En su lugar, el orden de los elementos \<COLUMN> de un archivo de formato determina el orden de las columnas del conjunto de filas resultante.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-171">Rather, the order of the \<COLUMN> elements in a format file determines the column order of the resultant rowset.</span></span> <span data-ttu-id="e8d1b-172">Los campos de datos se cargan en el orden en que los elementos \<COLUMN> correspondientes se declaran en el elemento \<COLUMN>.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-172">Data fields are loaded in the order in which the corresponding \<COLUMN> elements are declared in the \<COLUMN> element.</span></span>  
  
 <span data-ttu-id="e8d1b-173">Para obtener más información, vea [Cómo usa la importación en bloque el elemento \<ROW>](#HowUsesROW) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-173">For more information, see [How Bulk Import Uses the \<ROW> Element](#HowUsesROW), later in this topic.</span></span>  
  
 \<COLUMN>  
 <span data-ttu-id="e8d1b-174">Define una columna como un elemento (\<COLUMN>).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-174">Defines a column as an element (\<COLUMN>).</span></span> <span data-ttu-id="e8d1b-175">Cada elemento \<COLUMN> se corresponde a un elemento \<FIELD> (cuyo id. se especifica en el atributo SOURCE del elemento \<COLUMN>).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-175">Each \<COLUMN> element corresponds to a \<FIELD> element (whose ID is specified in the SOURCE attribute of the \<COLUMN> element).</span></span>  
  
 <span data-ttu-id="e8d1b-176">Los atributos de este elemento se tratan en la sección [Atributos del elemento \<COLUMN>](#AttrOfColumnElement) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-176">The attributes of this element are discussed in [Attributes of the \<COLUMN> Element](#AttrOfColumnElement), later in this topic.</span></span> <span data-ttu-id="e8d1b-177">Vea también [Cómo usa la importación en bloque el elemento \<COLUMN>](#HowUsesColumn) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-177">Also see, [How Bulk Import Uses the \<COLUMN> Element](#HowUsesColumn), later in this topic.</span></span>  
  
 \</BCPFORMAT>  
 <span data-ttu-id="e8d1b-178">Obligatorio para finalizar el archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-178">Required to end the format file.</span></span>  
  
####  <a name="attributes-of-the-field-element"></a><a name="AttrOfFieldElement"></a> <span data-ttu-id="e8d1b-179">Atributos del elemento \<FIELD></span><span class="sxs-lookup"><span data-stu-id="e8d1b-179">Attributes of the \<FIELD> Element</span></span>  
 <span data-ttu-id="e8d1b-180">En esta sección se describen los atributos del elemento \<FIELD>, que se resumen en la sintaxis de esquema siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8d1b-180">This section describes the attributes of the \<FIELD> element, which are summarized in the following schema syntax:</span></span>  
  
 <span data-ttu-id="e8d1b-181"><FIELD</span><span class="sxs-lookup"><span data-stu-id="e8d1b-181"><FIELD</span></span>  
  
 <span data-ttu-id="e8d1b-182">ID **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-182">ID **="*`fieldID`*"**</span></span>  
  
 <span data-ttu-id="e8d1b-183">XSi **:** Type **= " *`fieldType`* "**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-183">xsi **:** type **="*`fieldType`*"**</span></span>  
  
 <span data-ttu-id="e8d1b-184">[ LENGTH **="*`n`*"** ]</span><span class="sxs-lookup"><span data-stu-id="e8d1b-184">[ LENGTH **="*`n`*"** ]</span></span>  
  
 <span data-ttu-id="e8d1b-185">[PREFIX_LENGTH **= " *`p`* "** ]</span><span class="sxs-lookup"><span data-stu-id="e8d1b-185">[ PREFIX_LENGTH **="*`p`*"** ]</span></span>  
  
 <span data-ttu-id="e8d1b-186">[MAX_LENGTH **= " *`m`* "** ]</span><span class="sxs-lookup"><span data-stu-id="e8d1b-186">[ MAX_LENGTH **="*`m`*"** ]</span></span>  
  
 <span data-ttu-id="e8d1b-187">[COLLAtion **= " *`collationName`* "** ]</span><span class="sxs-lookup"><span data-stu-id="e8d1b-187">[ COLLATION **="*`collationName`*"** ]</span></span>  
  
 <span data-ttu-id="e8d1b-188">[TERMINATOR **= " *`terminator`* "** ]</span><span class="sxs-lookup"><span data-stu-id="e8d1b-188">[ TERMINATOR **="*`terminator`*"** ]</span></span>  
  
 />  
  
 <span data-ttu-id="e8d1b-189">Cada elemento \<FIELD> es independiente de los demás.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-189">Each \<FIELD> element is independent of the others.</span></span> <span data-ttu-id="e8d1b-190">Un campo se describe según los atributos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8d1b-190">A field is described in terms of the following attributes:</span></span>  
  
|<span data-ttu-id="e8d1b-191">Atributo de FIELD</span><span class="sxs-lookup"><span data-stu-id="e8d1b-191">FIELD Attribute</span></span>|<span data-ttu-id="e8d1b-192">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8d1b-192">Description</span></span>|<span data-ttu-id="e8d1b-193">Opcional /</span><span class="sxs-lookup"><span data-stu-id="e8d1b-193">Optional /</span></span><br /><br /> <span data-ttu-id="e8d1b-194">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e8d1b-194">Required</span></span>|  
|---------------------|-----------------|------------------------------|  
|<span data-ttu-id="e8d1b-195">ID **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-195">ID **="*`fieldID`*"**</span></span>|<span data-ttu-id="e8d1b-196">Especifica el nombre lógico del campo incluido en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-196">Specifies the logical name of the field in the data file.</span></span> <span data-ttu-id="e8d1b-197">El valor de ID de un campo es la clave utilizada para referirse al campo.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-197">The ID of a field is the key used to refer to the field.</span></span><br /><br /> <span data-ttu-id="e8d1b-198"><ID. de campo **= " *`fieldID`* "**/> se asigna a <columna source **= " *`fieldID`* "**/></span><span class="sxs-lookup"><span data-stu-id="e8d1b-198"><FIELD ID **="*`fieldID`*"**/> maps to <COLUMN SOURCE **="*`fieldID`*"**/></span></span>|<span data-ttu-id="e8d1b-199">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e8d1b-199">Required</span></span>|  
|<span data-ttu-id="e8d1b-200">xsi: Type **= " *`fieldType`* "**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-200">xsi:type **="*`fieldType`*"**</span></span>|<span data-ttu-id="e8d1b-201">Es una construcción XML (utilizada como atributo) que identifica el tipo de la instancia del elemento.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-201">This is an XML construct (used like an attribute) that identifies the type of the instance of the element.</span></span> <span data-ttu-id="e8d1b-202">El valor de *fieldType* determina qué atributos opcionales (a continuación) necesita el usuario en una instancia determinada.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-202">The value of *fieldType* determines which of the optional attributes (below) you need in a given instance.</span></span>|<span data-ttu-id="e8d1b-203">Obligatorio (en función del tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e8d1b-203">Required (depending on the data type)</span></span>|  
|<span data-ttu-id="e8d1b-204">LONGITUD **= " *`n`* "**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-204">LENGTH **="*`n`*"**</span></span>|<span data-ttu-id="e8d1b-205">Este atributo define la longitud de una instancia de un tipo de datos de longitud fija.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-205">This attribute defines the length for an instance of a fixed-length data type.</span></span><br /><br /> <span data-ttu-id="e8d1b-206">El valor de *n* debe ser un entero positivo.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-206">The value of *n* must be a positive integer.</span></span>|<span data-ttu-id="e8d1b-207">Opcional a no ser que el valor de xsi:type lo requiera</span><span class="sxs-lookup"><span data-stu-id="e8d1b-207">Optional unless required by the xsi:type value</span></span>|  
|<span data-ttu-id="e8d1b-208">PREFIX_LENGTH **= " *`p`* "**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-208">PREFIX_LENGTH **="*`p`*"**</span></span>|<span data-ttu-id="e8d1b-209">Este atributo define la longitud del prefijo para una representación de datos binarios.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-209">This attribute defines the prefix length for a binary data representation.</span></span> <span data-ttu-id="e8d1b-210">El valor de PREFIX_LENGTH, *p*, debe ser uno de los siguientes: 1, 2, 4 u 8.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-210">The PREFIX_LENGTH value, *p*, must be one of the following: 1, 2, 4, or 8.</span></span>|<span data-ttu-id="e8d1b-211">Opcional a no ser que el valor de xsi:type lo requiera</span><span class="sxs-lookup"><span data-stu-id="e8d1b-211">Optional unless required by the xsi:type value</span></span>|  
|<span data-ttu-id="e8d1b-212">MAX_LENGTH **= " *`m`* "**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-212">MAX_LENGTH **="*`m`*"**</span></span>|<span data-ttu-id="e8d1b-213">Este atributo es el número máximo de bytes que se pueden almacenar en un campo determinado.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-213">This attribute is the maximum number of bytes that can be stored in a given field.</span></span> <span data-ttu-id="e8d1b-214">Sin una tabla de destino, la longitud máxima de la columna se desconoce.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-214">Without a target table, the column max-length is not known.</span></span> <span data-ttu-id="e8d1b-215">El atributo MAX_LENGTH restringe la longitud máxima de una columna de caracteres de salida y limita el almacenamiento asignado al valor de la columna.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-215">The MAX_LENGTH attribute restricts the maximum length of an output character column, limiting the storage allocated for the column value.</span></span> <span data-ttu-id="e8d1b-216">Esto resulta especialmente útil al usar la opción BULK de la función OPENROWSET en una cláusula SELECT FROM.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-216">This is especially convenient when using the OPENROWSET function's BULK option in a SELECT FROM clause.</span></span><br /><br /> <span data-ttu-id="e8d1b-217">El valor de *m* debe ser un entero positivo.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-217">The value of *m* must be a positive integer.</span></span> <span data-ttu-id="e8d1b-218">De forma predeterminada, la longitud máxima es de 8.000 caracteres para una columna **char** y de 4.000 caracteres para una columna **nchar** .</span><span class="sxs-lookup"><span data-stu-id="e8d1b-218">By default, the maximum length is 8000 characters for a **char** column and 4000 characters for an **nchar** column.</span></span>|<span data-ttu-id="e8d1b-219">Opcional</span><span class="sxs-lookup"><span data-stu-id="e8d1b-219">Optional</span></span>|  
|<span data-ttu-id="e8d1b-220">COLLAtion **= " *`collationName`* "**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-220">COLLATION **="*`collationName`*"**</span></span>|<span data-ttu-id="e8d1b-221">COLLATION solo se permite para campos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-221">COLLATION is only allowed for character fields.</span></span> <span data-ttu-id="e8d1b-222">Para ver una lista de los nombres de intercalación de SQL, vea [Nombre de intercalación de SQL Server &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-222">For a list of the SQL collation names, see [SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql).</span></span>|<span data-ttu-id="e8d1b-223">Opcional</span><span class="sxs-lookup"><span data-stu-id="e8d1b-223">Optional</span></span>|  
|<span data-ttu-id="e8d1b-224">TERMINATOR **= " *`terminator`* "**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-224">TERMINATOR **= "*`terminator`*"**</span></span>|<span data-ttu-id="e8d1b-225">Este atributo especifica el terminador de un campo de datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-225">This attribute specifies the terminator of a data field.</span></span> <span data-ttu-id="e8d1b-226">El terminador puede ser cualquier carácter.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-226">The terminator can be any character.</span></span> <span data-ttu-id="e8d1b-227">Debe ser un carácter único que no forme parte de los datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-227">The terminator must be a unique character that is not part of the data.</span></span><br /><br /> <span data-ttu-id="e8d1b-228">De forma predeterminada, el terminador del campo es el carácter de tabulación (representado como \t).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-228">By default, the field terminator is the tab character (represented as \t).</span></span> <span data-ttu-id="e8d1b-229">Para representar una marca de párrafo, utilice \r\n.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-229">To represent a paragraph mark, use \r\n.</span></span>|<span data-ttu-id="e8d1b-230">Solo se usa con xsi:type de datos de caracteres, que requiere este atributo</span><span class="sxs-lookup"><span data-stu-id="e8d1b-230">Used only with an xsi:type of character data, which requires this attribute</span></span>|  
  
#####  <a name="xsitype-values-of-the-field-element"></a><a name="XsiTypeValuesOfFIELD"></a> <span data-ttu-id="e8d1b-231">Valores xsi:type del elemento \<FIELD></span><span class="sxs-lookup"><span data-stu-id="e8d1b-231">Xsi:type values of the \<FIELD> Element</span></span>  
 <span data-ttu-id="e8d1b-232">El valor xsi:type es una construcción XML (usada como atributo) que identifica el tipo de datos de una instancia de un elemento.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-232">The xsi:type value is an XML construct (used like an attribute) that identifies the data type of an instance of an element.</span></span> <span data-ttu-id="e8d1b-233">Para obtener más información acerca de su uso, vea "Colocar el valor xsi:type en un conjunto de datos", más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-233">For information on using the "Putting the xsi:type Value into a Data Set," later in this section.</span></span>  
  
 <span data-ttu-id="e8d1b-234">El valor xsi:type del elemento \<FIELD> admite los tipos de datos siguientes.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-234">The xsi:type value of the \<FIELD> element supports the following data types.</span></span>  
  
|<span data-ttu-id="e8d1b-235">Valores xsi:type de \<FIELD></span><span class="sxs-lookup"><span data-stu-id="e8d1b-235">\<FIELD> xsi:type values</span></span>|<span data-ttu-id="e8d1b-236">Atributos XML obligatorios</span><span class="sxs-lookup"><span data-stu-id="e8d1b-236">Required XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="e8d1b-237">para el tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e8d1b-237">for Data Type</span></span>|<span data-ttu-id="e8d1b-238">Atributos XML opcionales</span><span class="sxs-lookup"><span data-stu-id="e8d1b-238">Optional XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="e8d1b-239">para el tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e8d1b-239">for Data Type</span></span>|  
|-------------------------------|---------------------------------------------------|---------------------------------------------------|  
|<span data-ttu-id="e8d1b-240">**NativeFixed**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-240">**NativeFixed**</span></span>|`LENGTH`|<span data-ttu-id="e8d1b-241">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-241">None.</span></span>|  
|<span data-ttu-id="e8d1b-242">**NativePrefix**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-242">**NativePrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="e8d1b-243">MAX_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e8d1b-243">MAX_LENGTH</span></span>|  
|<span data-ttu-id="e8d1b-244">**CharFixed**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-244">**CharFixed**</span></span>|`LENGTH`|<span data-ttu-id="e8d1b-245">COLLATION</span><span class="sxs-lookup"><span data-stu-id="e8d1b-245">COLLATION</span></span>|  
|<span data-ttu-id="e8d1b-246">**NCharFixed**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-246">**NCharFixed**</span></span>|`LENGTH`|<span data-ttu-id="e8d1b-247">COLLATION</span><span class="sxs-lookup"><span data-stu-id="e8d1b-247">COLLATION</span></span>|  
|<span data-ttu-id="e8d1b-248">**CharPrefix**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-248">**CharPrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="e8d1b-249">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="e8d1b-249">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="e8d1b-250">**NCharPrefix**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-250">**NCharPrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="e8d1b-251">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="e8d1b-251">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="e8d1b-252">**CharTerm**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-252">**CharTerm**</span></span>|`TERMINATOR`|<span data-ttu-id="e8d1b-253">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="e8d1b-253">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="e8d1b-254">**NCharTerm**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-254">**NCharTerm**</span></span>|`TERMINATOR`|<span data-ttu-id="e8d1b-255">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="e8d1b-255">MAX_LENGTH, COLLATION</span></span>|  
  
 <span data-ttu-id="e8d1b-256">Para obtener más información sobre los tipos de datos de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Tipos de datos &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-256">For more information about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
####  <a name="attributes-of-the-column-element"></a><a name="AttrOfColumnElement"></a> <span data-ttu-id="e8d1b-257">Atributos del elemento \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="e8d1b-257">Attributes of the \<COLUMN> Element</span></span>  
 <span data-ttu-id="e8d1b-258">En esta sección se describen los atributos del elemento \<COLUMN>, que se resumen en la sintaxis de esquema siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8d1b-258">This section describes the attributes of the \<COLUMN> element, which are summarized in the following schema syntax:</span></span>  
  
 <span data-ttu-id="e8d1b-259">\<COLUMN</span><span class="sxs-lookup"><span data-stu-id="e8d1b-259">\<COLUMN</span></span>  
  
 <span data-ttu-id="e8d1b-260">SOURCE = "*fieldID*"</span><span class="sxs-lookup"><span data-stu-id="e8d1b-260">SOURCE = "*fieldID*"</span></span>  
  
 <span data-ttu-id="e8d1b-261">NAME = "*columnName*"</span><span class="sxs-lookup"><span data-stu-id="e8d1b-261">NAME = "*columnName*"</span></span>  
  
 <span data-ttu-id="e8d1b-262">xsi:type = "*columnType*"</span><span class="sxs-lookup"><span data-stu-id="e8d1b-262">xsi:type = "*columnType*"</span></span>  
  
 <span data-ttu-id="e8d1b-263">[ LENGTH = "*n*" ]</span><span class="sxs-lookup"><span data-stu-id="e8d1b-263">[ LENGTH = "*n*" ]</span></span>  
  
 <span data-ttu-id="e8d1b-264">[ PRECISION = "*n*" ]</span><span class="sxs-lookup"><span data-stu-id="e8d1b-264">[ PRECISION = "*n*" ]</span></span>  
  
 <span data-ttu-id="e8d1b-265">[ SCALE = "*value*" ]</span><span class="sxs-lookup"><span data-stu-id="e8d1b-265">[ SCALE = "*value*" ]</span></span>  
  
 <span data-ttu-id="e8d1b-266">[ NULLABLE = { "YES"</span><span class="sxs-lookup"><span data-stu-id="e8d1b-266">[ NULLABLE = { "YES"</span></span>  
  
 <span data-ttu-id="e8d1b-267">"NO" } ]</span><span class="sxs-lookup"><span data-stu-id="e8d1b-267">"NO" } ]</span></span>  
  
 />  
  
 <span data-ttu-id="e8d1b-268">Un campo se asigna a una columna de la tabla de destino mediante los atributos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8d1b-268">A field is mapped to a column in the target table using the following attributes:</span></span>  
  
|<span data-ttu-id="e8d1b-269">Atributo de COLUMN</span><span class="sxs-lookup"><span data-stu-id="e8d1b-269">COLUMN Attribute</span></span>|<span data-ttu-id="e8d1b-270">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8d1b-270">Description</span></span>|<span data-ttu-id="e8d1b-271">Opcional /</span><span class="sxs-lookup"><span data-stu-id="e8d1b-271">Optional /</span></span><br /><br /> <span data-ttu-id="e8d1b-272">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e8d1b-272">Required</span></span>|  
|----------------------|-----------------|------------------------------|  
|<span data-ttu-id="e8d1b-273">SOURCE **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-273">SOURCE **="*`fieldID`*"**</span></span>|<span data-ttu-id="e8d1b-274">Especifica el Id. del campo que se asigna a la columna.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-274">Specifies the ID of the field being mapped to the column.</span></span><br /><br /> <span data-ttu-id="e8d1b-275"><columna source **= " *`fieldID`* "**/> se asigna a <ID. de campo **= " *`fieldID`* "**/></span><span class="sxs-lookup"><span data-stu-id="e8d1b-275"><COLUMN SOURCE **="*`fieldID`*"**/> maps to <FIELD ID **="*`fieldID`*"**/></span></span>|<span data-ttu-id="e8d1b-276">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e8d1b-276">Required</span></span>|  
|<span data-ttu-id="e8d1b-277">NAME = "*columnName*"</span><span class="sxs-lookup"><span data-stu-id="e8d1b-277">NAME = "*columnName*"</span></span>|<span data-ttu-id="e8d1b-278">Especifica el nombre de la columna en el conjunto de filas representado por el archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-278">Specifies the name of the column in the row set represented by the format file.</span></span> <span data-ttu-id="e8d1b-279">Este nombre de columna se utiliza para identificar la columna en el conjunto de resultados y no es necesario que corresponda al nombre de columna usado en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-279">This column name is used to identify the column in the result set, and it need not correspond to the column name used in the target table.</span></span>|<span data-ttu-id="e8d1b-280">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="e8d1b-280">Required</span></span>|  
|<span data-ttu-id="e8d1b-281">XSi **:** Type **= " *`ColumnType`* "**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-281">xsi **:** type **="*`ColumnType`*"**</span></span>|<span data-ttu-id="e8d1b-282">Es una construcción XML (utilizada como atributo) que identifica el tipo de datos de la instancia del elemento.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-282">This is an XML construct (used like an attribute) that identifies the data type of the instance of the element.</span></span> <span data-ttu-id="e8d1b-283">El valor de *ColumnType* determina qué atributos opcionales (a continuación) necesita el usuario en una instancia determinada.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-283">The value of *ColumnType* determines which of the optional attributes (below) you need in a given instance.</span></span><br /><br /> <span data-ttu-id="e8d1b-284">Nota: los valores posibles de *ColumnType* y sus atributos asociados se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-284">Note: The possible values of *ColumnType* and their associated attributes are listed in the next table.</span></span>|<span data-ttu-id="e8d1b-285">Opcional</span><span class="sxs-lookup"><span data-stu-id="e8d1b-285">Optional</span></span>|  
|<span data-ttu-id="e8d1b-286">LONGITUD **= " *`n`* "**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-286">LENGTH **="*`n`*"**</span></span>|<span data-ttu-id="e8d1b-287">Define la longitud de una instancia de un tipo de datos de longitud fija.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-287">Defines the length for an instance of a fixed-length data type.</span></span> <span data-ttu-id="e8d1b-288">LENGTH se utiliza solo cuando xsi:type es un tipo de datos de cadena.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-288">LENGTH is used only when the xsi:type is a string data type.</span></span><br /><br /> <span data-ttu-id="e8d1b-289">El valor de *n* debe ser un entero positivo.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-289">The value of *n* must be a positive integer.</span></span>|<span data-ttu-id="e8d1b-290">Opcional (solo disponible si xsi:type es un tipo de datos de cadena)</span><span class="sxs-lookup"><span data-stu-id="e8d1b-290">Optional (available only if the xsi:type is a string data type)</span></span>|  
|<span data-ttu-id="e8d1b-291">PRECISION **="*`n`*"**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-291">PRECISION **="*`n`*"**</span></span>|<span data-ttu-id="e8d1b-292">Indica el número de dígitos de un número.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-292">Indicates the number of digits in a number.</span></span> <span data-ttu-id="e8d1b-293">Por ejemplo, el número 123,45 tiene una precisión de 5.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-293">For example, the number 123.45 has a precision of 5.</span></span><br /><br /> <span data-ttu-id="e8d1b-294">El valor debe ser un entero positivo.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-294">The value must be a positive integer.</span></span>|<span data-ttu-id="e8d1b-295">Opcional (solo disponible si xsi:type es un tipo de datos de número variable)</span><span class="sxs-lookup"><span data-stu-id="e8d1b-295">Optional (available only if the xsi:type is a variable-number data type)</span></span>|  
|<span data-ttu-id="e8d1b-296">ESCALA **= " *`int`* "**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-296">SCALE **="*`int`*"**</span></span>|<span data-ttu-id="e8d1b-297">Indica el número de dígitos situados a la derecha de la coma decimal de un número.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-297">Indicates the number of digits to the right of the decimal point in a number.</span></span> <span data-ttu-id="e8d1b-298">Por ejemplo, el número 123,45 tiene una escala de 2.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-298">For example, the number 123.45 has a scale of 2.</span></span><br /><br /> <span data-ttu-id="e8d1b-299">El valor debe ser un entero.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-299">The value must be an integer.</span></span>|<span data-ttu-id="e8d1b-300">Opcional (solo disponible si xsi:type es un tipo de datos de número variable)</span><span class="sxs-lookup"><span data-stu-id="e8d1b-300">Optional (available only if the xsi:type is a variable-number data type)</span></span>|  
|<span data-ttu-id="e8d1b-301">NULLABLE **=** { **"** YES **"**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-301">NULLABLE **=** { **"** YES **"**</span></span><br /><br /> <span data-ttu-id="e8d1b-302">**"** NO **"** }</span><span class="sxs-lookup"><span data-stu-id="e8d1b-302">**"** NO **"** }</span></span>|<span data-ttu-id="e8d1b-303">Indica si una columna puede aceptar valores NULL.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-303">Indicates whether a column can assume NULL values.</span></span> <span data-ttu-id="e8d1b-304">Este atributo es completamente independiente de FIELDS.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-304">This attribute is completely independent of FIELDS.</span></span> <span data-ttu-id="e8d1b-305">No obstante, si una columna tiene el valor de NULLABLE establecido en NO y el campo especifica NULL (es decir, no especifica ningún valor), se produce un error de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-305">However, if a column is not NULLABLE and field specifies NULL (by not specifying any value), a run-time error results.</span></span><br /><br /> <span data-ttu-id="e8d1b-306">El atributo NULLABLE solo se usa si escribe una instrucción SELECT FROM OPENROWSET(BULK...) simple.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-306">The NULLABLE attribute is used only if you do a plain SELECT FROM OPENROWSET(BULK...) statement.</span></span>|<span data-ttu-id="e8d1b-307">Opcional (disponible para cualquier tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="e8d1b-307">Optional (available for any data type)</span></span>|  
  
#####  <a name="xsitype-values-of-the-column-element"></a><a name="XsiTypeValuesOfCOLUMN"></a> <span data-ttu-id="e8d1b-308">Valores xsi:type del elemento \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="e8d1b-308">Xsi:type values of the \<COLUMN> Element</span></span>  
 <span data-ttu-id="e8d1b-309">El valor xsi:type es una construcción XML (usada como atributo) que identifica el tipo de datos de una instancia de un elemento.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-309">The xsi:type value is an XML construct (used like an attribute) that identifies the data type of an instance of an element.</span></span> <span data-ttu-id="e8d1b-310">Para obtener más información acerca de su uso, vea "Colocar el valor xsi:type en un conjunto de datos", más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-310">For information on using the "Putting the xsi:type Value into a Data Set," later in this section.</span></span>  
  
 <span data-ttu-id="e8d1b-311">El elemento \<COLUMN> admite tipos de datos SQL nativos, de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8d1b-311">The \<COLUMN> element supports native SQL data types, as follows:</span></span>  
  
|<span data-ttu-id="e8d1b-312">Categoría de tipo</span><span class="sxs-lookup"><span data-stu-id="e8d1b-312">Type Category</span></span>|<span data-ttu-id="e8d1b-313">Tipos de datos de \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="e8d1b-313">\<COLUMN> Data Types</span></span>|<span data-ttu-id="e8d1b-314">Atributos XML obligatorios</span><span class="sxs-lookup"><span data-stu-id="e8d1b-314">Required XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="e8d1b-315">para el tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e8d1b-315">for Data Type</span></span>|<span data-ttu-id="e8d1b-316">Atributos XML opcionales</span><span class="sxs-lookup"><span data-stu-id="e8d1b-316">Optional XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="e8d1b-317">para el tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e8d1b-317">for Data Type</span></span>|  
|-------------------|---------------------------|---------------------------------------------------|---------------------------------------------------|  
|<span data-ttu-id="e8d1b-318">Corregido</span><span class="sxs-lookup"><span data-stu-id="e8d1b-318">Fixed</span></span>|<span data-ttu-id="e8d1b-319">`SQLBIT`, `SQLTINYINT`, `SQLSMALLINT`, `SQLINT`, `SQLBIGINT`, `SQLFLT4`, `SQLFLT8`, `SQLDATETIME`, `SQLDATETIM4`, `SQLDATETIM8`, `SQLMONEY`, `SQLMONEY4`, `SQLVARIANT` y `SQLUNIQUEID`</span><span class="sxs-lookup"><span data-stu-id="e8d1b-319">`SQLBIT`, `SQLTINYINT`, `SQLSMALLINT`, `SQLINT`, `SQLBIGINT`, `SQLFLT4`, `SQLFLT8`, `SQLDATETIME`, `SQLDATETIM4`, `SQLDATETIM8`, `SQLMONEY`, `SQLMONEY4`, `SQLVARIANT`, and `SQLUNIQUEID`</span></span>|<span data-ttu-id="e8d1b-320">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-320">None.</span></span>|<span data-ttu-id="e8d1b-321">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e8d1b-321">NULLABLE</span></span>|  
|<span data-ttu-id="e8d1b-322">Número de variable</span><span class="sxs-lookup"><span data-stu-id="e8d1b-322">Variable Number</span></span>|<span data-ttu-id="e8d1b-323">`SQLDECIMAL` y `SQLNUMERIC`</span><span class="sxs-lookup"><span data-stu-id="e8d1b-323">`SQLDECIMAL` and `SQLNUMERIC`</span></span>|<span data-ttu-id="e8d1b-324">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-324">None.</span></span>|<span data-ttu-id="e8d1b-325">NULLABLE, PRECISION, SCALE</span><span class="sxs-lookup"><span data-stu-id="e8d1b-325">NULLABLE, PRECISION, SCALE</span></span>|  
|<span data-ttu-id="e8d1b-326">LOB</span><span class="sxs-lookup"><span data-stu-id="e8d1b-326">LOB</span></span>|<span data-ttu-id="e8d1b-327">`SQLIMAGE`, `CharLOB`, `SQLTEXT` y `SQLUDT`.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-327">`SQLIMAGE`, `CharLOB`, `SQLTEXT`, and `SQLUDT`</span></span>|<span data-ttu-id="e8d1b-328">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-328">None.</span></span>|<span data-ttu-id="e8d1b-329">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e8d1b-329">NULLABLE</span></span>|  
|<span data-ttu-id="e8d1b-330">LOB de caracteres</span><span class="sxs-lookup"><span data-stu-id="e8d1b-330">Character LOB</span></span>|`SQLNTEXT`|<span data-ttu-id="e8d1b-331">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-331">None.</span></span>|<span data-ttu-id="e8d1b-332">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e8d1b-332">NULLABLE</span></span>|  
|<span data-ttu-id="e8d1b-333">Cadena binaria</span><span class="sxs-lookup"><span data-stu-id="e8d1b-333">Binary string</span></span>|<span data-ttu-id="e8d1b-334">`SQLBINARY` y `SQLVARYBIN`</span><span class="sxs-lookup"><span data-stu-id="e8d1b-334">`SQLBINARY` and `SQLVARYBIN`</span></span>|<span data-ttu-id="e8d1b-335">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-335">None.</span></span>|<span data-ttu-id="e8d1b-336">NULLABLE, LENGTH</span><span class="sxs-lookup"><span data-stu-id="e8d1b-336">NULLABLE, LENGTH</span></span>|  
|<span data-ttu-id="e8d1b-337">Cadena de caracteres</span><span class="sxs-lookup"><span data-stu-id="e8d1b-337">Character string</span></span>|<span data-ttu-id="e8d1b-338">`SQLCHAR`, `SQLVARYCHAR`, `SQLNCHAR` y `SQLNVARCHAR`.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-338">`SQLCHAR`, `SQLVARYCHAR`, `SQLNCHAR`, and `SQLNVARCHAR`</span></span>|<span data-ttu-id="e8d1b-339">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-339">None.</span></span>|<span data-ttu-id="e8d1b-340">NULLABLE, LENGTH</span><span class="sxs-lookup"><span data-stu-id="e8d1b-340">NULLABLE, LENGTH</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e8d1b-341">Para importar o exportar de forma masiva datos SQLXML, utilice uno de los tipos de datos siguientes en el archivo de formato: SQLCHAR o SQLVARYCHAR (los datos se envían en la página de códigos del cliente o en la página de códigos implícita en la intercalación), SQLNCHAR o SQLNVARCHAR (los datos se envían como Unicode), o SQLBINARY o SQLVARYBIN (los datos se envían sin ninguna conversión).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-341">To bulk export or import SQLXML data, use one of the following data types in your format file: SQLCHAR or SQLVARYCHAR (the data is sent in the client code page or in the code page implied by the collation), SQLNCHAR or SQLNVARCHAR (the data is sent as Unicode), or SQLBINARY or SQLVARYBIN (the data is sent without any conversion).</span></span>  
  
 <span data-ttu-id="e8d1b-342">Para obtener más información sobre los tipos de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vea [Tipos de datos &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-342">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
###  <a name="how-bulk-import-uses-the-row-element"></a><a name="HowUsesROW"></a> <span data-ttu-id="e8d1b-343">Cómo usa la importación en bloque el elemento \<ROW></span><span class="sxs-lookup"><span data-stu-id="e8d1b-343">How Bulk Import Uses the \<ROW> Element</span></span>  
 <span data-ttu-id="e8d1b-344">El elemento \<ROW> se omite en algunos contextos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-344">The \<ROW> element is ignored in some contexts.</span></span> <span data-ttu-id="e8d1b-345">El hecho de que un elemento \<ROW> afecte a una operación de importación en bloque depende de cómo se realice la operación:</span><span class="sxs-lookup"><span data-stu-id="e8d1b-345">Whether the \<ROW> element affects a bulk-import operation depends on how the operation is performed:</span></span>  
  
-   <span data-ttu-id="e8d1b-346">Comando **bcp**</span><span class="sxs-lookup"><span data-stu-id="e8d1b-346">the **bcp** command</span></span>  
  
     <span data-ttu-id="e8d1b-347">Al cargar datos en una tabla de destino, **bcp** omite el componente \<ROW>.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-347">When data is loaded into a target table, **bcp** ignores the \<ROW> component.</span></span> <span data-ttu-id="e8d1b-348">En su lugar, **bcp** carga los datos en función de los tipos de columnas de la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-348">Instead, **bcp** loads the data based on the column types of the target table.</span></span>  
  
-   [!INCLUDE[tsql](../../../includes/tsql-md.md)] <span data-ttu-id="e8d1b-349">instrucciones (proveedor de conjuntos de filas BULK de BULK INSERT y OPENROWSET)</span><span class="sxs-lookup"><span data-stu-id="e8d1b-349">statements (BULK INSERT and OPENROWSET's Bulk rowset provider)</span></span>  
  
     <span data-ttu-id="e8d1b-350">Al realizar una importación en bloque de datos en una tabla, las instrucciones [!INCLUDE[tsql](../../../includes/tsql-md.md)] usan el componente \<ROW> para generar el conjunto de filas de entrada.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-350">When bulk importing data into a table, [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements use the \<ROW> component to generate the input rowset.</span></span> <span data-ttu-id="e8d1b-351">Además, las instrucciones [!INCLUDE[tsql](../../../includes/tsql-md.md)] realizan las conversiones de tipos adecuadas en función de los tipos de columna especificados en \<ROW> y de la columna correspondiente en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-351">Also, [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements perform appropriate type conversions based on the column types specified under \<ROW> and the corresponding column in the target table.</span></span> <span data-ttu-id="e8d1b-352">Si los tipos de columna especificados en el archivo de formato y la tabla de destino no coinciden, se realiza una conversión de tipo adicional.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-352">If a mismatch exists between column types as specified in the format file and in the target table, an extra type conversion occurs.</span></span> <span data-ttu-id="e8d1b-353">Esta conversión de tipo adicional puede llevar a discrepancias (es decir, a una pérdida de precisión) en cuanto al comportamiento en el proveedor de conjuntos de filas BULK de OPENROWSET o BULK INSERT en comparación con **bcp**.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-353">This extra type conversion may lead to some discrepancy (that is, a loss of precision) in behavior in BULK INSERT or OPENROWSET's Bulk rowset provider as compared to **bcp**.</span></span>  
  
     <span data-ttu-id="e8d1b-354">La información del elemento \<ROW> permite construir una fila sin necesidad de información adicional.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-354">The information in the \<ROW> element allows a row to be constructed without requiring any additional information.</span></span> <span data-ttu-id="e8d1b-355">Por este motivo, puede generar un conjunto de filas mediante una instrucción SELECT (SELECT \* FROM OPENROWSET(BULK *datafile* FORMATFILE=*xmlformatfile*).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-355">For this reason, you can generate a rowset using a SELECT statement (SELECT \* FROM OPENROWSET(BULK *datafile* FORMATFILE=*xmlformatfile*).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8d1b-356">La cláusula OPENROWSET BULK requiere un archivo de formato (tenga en cuenta que solo se puede convertir desde el tipo de datos del campo al tipo de datos de una columna con un archivo de formato XML).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-356">The OPENROWSET BULK clause requires a format file (note that converting from the data type of the field to the data type of a column is available only with an XML format file).</span></span>  
  
###  <a name="how-bulk-import-uses-the-column-element"></a><a name="HowUsesColumn"></a> <span data-ttu-id="e8d1b-357">Cómo usa la importación en bloque el elemento \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="e8d1b-357">How Bulk Import Uses the \<COLUMN> Element</span></span>  
 <span data-ttu-id="e8d1b-358">Para la importación en bloque de datos en una tabla, los elementos \<COLUMN> de un archivo de formato asignan un campo de archivo de datos a columnas de tabla mediante la especificación de:</span><span class="sxs-lookup"><span data-stu-id="e8d1b-358">For bulk importing data into a table, the \<COLUMN> elements in a format file map a data-file field to table columns by specifying:</span></span>  
  
-   <span data-ttu-id="e8d1b-359">La posición de cada campo dentro de una fila del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-359">The position of each field within a row in the data file.</span></span>  
  
-   <span data-ttu-id="e8d1b-360">El tipo de columna, que se utiliza para convertir el tipo de datos de campo al tipo de datos de columna deseado.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-360">The column type, which is used to convert the field data type to the desired column data type.</span></span>  
  
 <span data-ttu-id="e8d1b-361">Si un campo no tiene asignada ninguna columna, el campo no se copia en las filas generadas.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-361">If no column is mapped to a field, the field is not copied into the generated row(s).</span></span> <span data-ttu-id="e8d1b-362">Este comportamiento permite a un archivo de datos generar filas con distintas columnas (en tablas diferentes).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-362">This behavior allows a data file to generate rows with different columns (in different tables).</span></span>  
  
 <span data-ttu-id="e8d1b-363">De forma similar, para exportar de forma masiva datos de una tabla, cada elemento \<COLUMN> del archivo de formato asigna la columna de la fila de la tabla de entrada a su campo correspondiente en el archivo de datos de salida.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-363">Similarly, for bulk exporting data from a table, each \<COLUMN> in the format file maps the column from the input table row to its corresponding field in the output data file.</span></span>  
  
###  <a name="putting-the-xsitype-value-into-a-data-set"></a><a name="PutXsiTypeValueIntoDataSet"></a> <span data-ttu-id="e8d1b-364">Colocar el valor xsi:type en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="e8d1b-364">Putting the xsi:type Value into a Data Set</span></span>  
 <span data-ttu-id="e8d1b-365">Si un documento XML se valida con el lenguaje de definición de esquema XML (XSD), el valor xsi:type no se coloca en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-365">When an XML document is validated through the XML Schema Definition (XSD) language, the xsi:type value is not put into the data set.</span></span> <span data-ttu-id="e8d1b-366">No obstante, puede colocar la información de xsi:type en el conjunto de datos si carga el archivo de formato XML en un documento XML (por ejemplo, `myDoc`), tal como ilustra el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="e8d1b-366">However, you can put the xsi:type information into the data set by loading the XML format file into an XML document (for example, `myDoc`), as illustrated in the following code snippet:</span></span>  
  
```  
...;  
myDoc.LoadXml(xmlFormat);  
XmlNodeList ColumnList = myDoc.GetElementsByTagName("COLUMN");  
for(int i=0;i<ColumnList.Count;i++)  
{  
   Console.Write("COLUMN: xsi:type=" +ColumnList[i].Attributes["type",  
      "http://www.w3.org/2001/XMLSchema-instance"].Value+"\n");  
}  
```  
  
##  <a name="sample-xml-format-files"></a><a name="SampleXmlFFs"></a> <span data-ttu-id="e8d1b-367">Archivos de formato XML de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8d1b-367">Sample XML Format Files</span></span>  
 <span data-ttu-id="e8d1b-368">Esta sección contiene información sobre el uso de archivos de formato XML en diversos casos, incluido un ejemplo de [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e8d1b-368">This section contains information on using XML format files in a variety of cases, including an [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8d1b-369">En los archivos de datos que se muestran en los ejemplos siguientes, `<tab>` indica un carácter de tabulación en un archivo de datos y `<return>` indica un retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-369">In the data files shown in the following examples, `<tab>` indicates a tab character in a data file, and `<return>` indicates a carriage return.</span></span>  
  

  
> [!NOTE]  
>  <span data-ttu-id="e8d1b-370">Para obtener información sobre cómo crear archivos de formato, vea [Crear un archivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-370">For information about how to create format files, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
###  <a name="a-ordering-character-data-fields-the-same-as-table-columns"></a><a name="OrderCharFieldsSameAsCols"></a> <span data-ttu-id="e8d1b-371">A.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-371">A.</span></span> <span data-ttu-id="e8d1b-372">Ordenar campos de datos de caracteres igual que columnas de tabla</span><span class="sxs-lookup"><span data-stu-id="e8d1b-372">Ordering character-data fields the same as table columns</span></span>  
 <span data-ttu-id="e8d1b-373">En el ejemplo siguiente se muestra un archivo de formato XML que describe un archivo de datos que contiene tres campos de datos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-373">The following example shows an XML format file that describes a data file containing three fields of character data.</span></span> <span data-ttu-id="e8d1b-374">El archivo de formato asigna el archivo de datos a una tabla que contiene tres columnas.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-374">The format file maps the data file to a table that contains three columns.</span></span> <span data-ttu-id="e8d1b-375">Los campos de datos se corresponden uno a uno con las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-375">The data fields correspond one-to-one with the columns of the table.</span></span>  
  
 <span data-ttu-id="e8d1b-376">**Tabla (fila):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span><span class="sxs-lookup"><span data-stu-id="e8d1b-376">**Table (row):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span></span>  
  
 <span data-ttu-id="e8d1b-377">**Archivo de datos (registro):** Age\<tab>Firstname\<tab>Lastname\<return></span><span class="sxs-lookup"><span data-stu-id="e8d1b-377">**Data file (record):** Age\<tab>Firstname\<tab>Lastname\<return></span></span>  
  
 <span data-ttu-id="e8d1b-378">El siguiente archivo de formato XML lee del archivo de datos a la tabla.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-378">The following XML format file reads from the data file to the table.</span></span>  
  
 <span data-ttu-id="e8d1b-379">En el elemento `<RECORD>` , el archivo de formato representa los valores de datos de los tres campos como datos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-379">In the `<RECORD>` element, the format file represents the data values in all three fields as character data.</span></span> <span data-ttu-id="e8d1b-380">Para cada campo, el atributo `TERMINATOR` indica el terminador que sigue al valor de datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-380">For each field, the `TERMINATOR` attribute indicates the terminator that follows the data value.</span></span>  
  
 <span data-ttu-id="e8d1b-381">Los campos de datos se corresponden uno a uno con las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-381">The data fields correspond one-to-one with the columns of the table.</span></span> <span data-ttu-id="e8d1b-382">En el elemento `<ROW>` , el archivo de formato asigna la columna `Age` al primer campo, la columna `FirstName` al segundo campo y la columna `LastName` al tercer campo.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-382">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the second field, and the column `LastName` to the third field.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>   
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="20" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="2" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="3" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="e8d1b-383">Para ver un ejemplo equivalente de [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , vea [Crear un archivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-383">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
###  <a name="b-ordering-data-fields-and-table-columns-differently"></a><a name="OrderFieldsAndColsDifferently"></a> <span data-ttu-id="e8d1b-384">B.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-384">B.</span></span> <span data-ttu-id="e8d1b-385">Ordenar campos de datos y columnas de tabla de forma diferente</span><span class="sxs-lookup"><span data-stu-id="e8d1b-385">Ordering data fields and table columns differently</span></span>  
 <span data-ttu-id="e8d1b-386">En el ejemplo siguiente se muestra un archivo de formato XML que describe un archivo de datos que contiene tres campos de datos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-386">The following example shows an XML format file that describes a data file containing three fields of character data.</span></span> <span data-ttu-id="e8d1b-387">El archivo de formato asigna el archivo de datos a una tabla que contiene tres columnas que están ordenadas de forma diferente a los campos del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-387">The format file maps the data file to a table that contains three columns that are ordered differently from the fields of the data file.</span></span>  
  
 <span data-ttu-id="e8d1b-388">**Tabla (fila):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span><span class="sxs-lookup"><span data-stu-id="e8d1b-388">**Table (row):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span></span>  
  
 <span data-ttu-id="e8d1b-389">**Archivo de datos** (registro): Age\<tab>Lastname\<tab>Firstname\<return></span><span class="sxs-lookup"><span data-stu-id="e8d1b-389">**Data file** (record): Age\<tab>Lastname\<tab>Firstname\<return></span></span>  
  
 <span data-ttu-id="e8d1b-390">En el elemento `<RECORD>` , el archivo de formato representa los valores de datos de los tres campos como datos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-390">In the `<RECORD>` element, the format file represents the data values in all three fields as character data.</span></span>  
  
 <span data-ttu-id="e8d1b-391">En el elemento `<ROW>` , el archivo de formato asigna la columna `Age` al primer campo, la columna `FirstName` al tercer campo y la columna `LastName` al segundo campo.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-391">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the third field, and the column `LastName` to the second field.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>  
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="20"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="3" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="2" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="e8d1b-392">Para ver un ejemplo equivalente de [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , vea [Usar un archivo de formato para asignar columnas de tabla a campos de un archivo de datos &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-392">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md).</span></span>  
  
### <a name="c-omitting-a-data-field"></a><span data-ttu-id="e8d1b-393">C.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-393">C.</span></span> <span data-ttu-id="e8d1b-394">Omitir un campo de datos</span><span class="sxs-lookup"><span data-stu-id="e8d1b-394">Omitting a data field</span></span>  
 <span data-ttu-id="e8d1b-395">En el ejemplo siguiente se muestra un archivo de formato XML que describe un archivo de datos que contiene cuatro campos de datos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-395">The following example shows an XML format file that describes a data file containing four fields of character data.</span></span> <span data-ttu-id="e8d1b-396">El archivo de formato asigna el archivo de datos a una tabla que contiene tres columnas.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-396">The format file maps the data file to a table that contains three columns.</span></span> <span data-ttu-id="e8d1b-397">El segundo campo de datos no se corresponde con ninguna columna de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-397">The second data field does not correspond to any table column.</span></span>  
  
 <span data-ttu-id="e8d1b-398">**Tabla (fila):** Person (Age int, FirstName Varchar(20), LastName Varchar(30))</span><span class="sxs-lookup"><span data-stu-id="e8d1b-398">**Table (row):** Person (Age int, FirstName Varchar(20), LastName Varchar(30))</span></span>  
  
 <span data-ttu-id="e8d1b-399">**Archivo de datos (registro):** Age\<tab>employeeID\<tab>Firstname\<tab>Lastname\<return></span><span class="sxs-lookup"><span data-stu-id="e8d1b-399">**Data file (record):** Age\<tab>employeeID\<tab>Firstname\<tab>Lastname\<return></span></span>  
  
 <span data-ttu-id="e8d1b-400">En el elemento `<RECORD>` , el archivo de formato representa los valores de datos de los cuatro campos como datos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-400">In the `<RECORD>` element, the format file represents the data values in all four fields as character data.</span></span> <span data-ttu-id="e8d1b-401">Para cada campo, el atributo TERMINATOR indica el terminador que sigue al valor de datos.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-401">For each field, the TERMINATOR attribute indicates the terminator that follows the data value.</span></span>  
  
 <span data-ttu-id="e8d1b-402">En el elemento `<ROW>` , el archivo de formato asigna la columna `Age` al primer campo, la columna `FirstName` al tercer campo y la columna `LastName` al cuarto campo.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-402">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the third field, and the column `LastName` to the fourth field.</span></span>  
  
```  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>  
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="10"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="20"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="3" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="4" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="e8d1b-403">Para ver un ejemplo equivalente de [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , vea [Usar un archivo de formato para omitir un campo de datos &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e8d1b-403">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Use a Format File to Skip a Data Field &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md).</span></span>  
  
###  <a name="d-mapping-field-xsitype-to-column-xsitype"></a><a name="MapXSItype"></a> <span data-ttu-id="e8d1b-404">D.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-404">D.</span></span> <span data-ttu-id="e8d1b-405">Asignación de \<FIELD> xsi:type a \<COLUMN> xsi:type</span><span class="sxs-lookup"><span data-stu-id="e8d1b-405">Mapping \<FIELD> xsi:type to \<COLUMN> xsi:type</span></span>  
 <span data-ttu-id="e8d1b-406">En el ejemplo siguiente se muestran tipos de campos diferentes y sus asignaciones a columnas.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-406">The following example shows different types of fields and their mappings to columns.</span></span>  
  
```  
<?xml version = "1.0"?>  
<BCPFORMAT  
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
   <RECORD>  
      <FIELD xsi:type="CharTerm" ID="C1" TERMINATOR="\t"   
            MAX_LENGTH="4"/>  
      <FIELD xsi:type="CharFixed" ID="C2" LENGTH="10"   
         COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="CharPrefix" ID="C3" PREFIX_LENGTH="2"   
         MAX_LENGTH="32" COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NCharTerm" ID="C4" TERMINATOR="\t"   
         MAX_LENGTH="4"/>  
      <FIELD xsi:type="NCharFixed" ID="C5" LENGTH="10"   
         COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NCharPrefix" ID="C6" PREFIX_LENGTH="2"   
         MAX_LENGTH="32" COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NativeFixed" ID="C7" LENGTH="4"/>  
   </RECORD>  
   <ROW>  
      <COLUMN SOURCE="C1" NAME="Age" xsi:type="SQLTINYINT"/>  
      <COLUMN SOURCE="C2" NAME="FirstName" xsi:type="SQLVARYCHAR"   
      LENGTH="16" NULLABLE="NO"/>  
      <COLUMN SOURCE="C3" NAME="LastName" />  
      <COLUMN SOURCE="C4" NAME="Salary" xsi:type="SQLMONEY"/>  
      <COLUMN SOURCE="C5" NAME="Picture" xsi:type="SQLIMAGE"/>  
      <COLUMN SOURCE="C6" NAME="Bio" xsi:type="SQLTEXT"/>  
      <COLUMN SOURCE="C7" NAME="Interest"xsi:type="SQLDECIMAL"   
      PRECISION="5" SCALE="3"/>  
   </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="e-mapping-xml-data-to-a-table"></a><a name="MapXMLDataToTbl"></a> <span data-ttu-id="e8d1b-407">E.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-407">E.</span></span> <span data-ttu-id="e8d1b-408">Asignar datos XML a una tabla</span><span class="sxs-lookup"><span data-stu-id="e8d1b-408">Mapping XML data to a table</span></span>  
 <span data-ttu-id="e8d1b-409">En el ejemplo siguiente se crea una tabla vacía de dos columnas (`t_xml`), en la que la primera columna se asigna al tipo de datos `int` y la segunda columna se asigna al tipo de datos `xml` .</span><span class="sxs-lookup"><span data-stu-id="e8d1b-409">The following example creates an empty two-column table (`t_xml`), in which the first column maps to the `int` data type and the second column maps to the `xml` data type.</span></span>  
  
```  
CREATE TABLE t_xml (c1 int, c2 xml)  
```  
  
 <span data-ttu-id="e8d1b-410">El siguiente archivo de formato XML carga un archivo de datos en una tabla `t_xml`.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-410">The following XML format file would load a data file into table `t_xml`.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="NativePrefix" PREFIX_LENGTH="1"/>  
  <FIELD ID="2" xsi:type="NCharPrefix" PREFIX_LENGTH="8"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="c1" xsi:type="SQLINT"/>  
  <COLUMN SOURCE="2" NAME="c2" xsi:type="SQLNCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="f-importing-fixed-length-or-fixed-width-fields"></a><a name="ImportFixedFields"></a> <span data-ttu-id="e8d1b-411">F.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-411">F.</span></span> <span data-ttu-id="e8d1b-412">Importar campos de longitud fija o de ancho fijo</span><span class="sxs-lookup"><span data-stu-id="e8d1b-412">Importing fixed-length or fixed-width fields</span></span>  
 <span data-ttu-id="e8d1b-413">En el siguiente ejemplo se describen campos fijos de `10` o `6` caracteres cada uno.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-413">The following example describes fixed fields of `10` or `6` characters each.</span></span> <span data-ttu-id="e8d1b-414">El archivo de formato representa estas longitudes y anchos de campo como `LENGTH="10"` y `LENGTH="6"`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-414">The format file represents these field lengths/widths as `LENGTH="10"` and `LENGTH="6"`, respectively.</span></span> <span data-ttu-id="e8d1b-415">Cada una de las filas de los archivos de datos termina con una combinación de retorno de carro y avance de línea, {CR}{LF}, que el archivo de formato representa como `TERMINATOR="\r\n"`.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-415">Every row of the data files ends with a carriage return-line feed combination, {CR}{LF}, which the format file represents as `TERMINATOR="\r\n"`.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT  
       xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"  
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharFixed" LENGTH="10"/>  
    <FIELD ID="2" xsi:type="CharFixed" LENGTH="6"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="C1" xsi:type="SQLINT" />  
    <COLUMN SOURCE="2" NAME="C2" xsi:type="SQLINT" />  
  </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="additional-examples"></a><a name="AdditionalExamples"></a> <span data-ttu-id="e8d1b-416">Otros ejemplos</span><span class="sxs-lookup"><span data-stu-id="e8d1b-416">Additional Examples</span></span>  
 <span data-ttu-id="e8d1b-417">Para obtener más ejemplos tanto de archivos de formato XML como de formato no XML, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="e8d1b-417">For additional examples of both non-XML format files and XML format files, see the following topics:</span></span>  
  
-   [<span data-ttu-id="e8d1b-418">Usar un archivo de formato para omitir una columna de tabla &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e8d1b-418">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="e8d1b-419">Usar un archivo de formato para omitir un campo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e8d1b-419">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="e8d1b-420">Usar un archivo de formato para asignar columnas de tabla a campos de un archivo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e8d1b-420">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e8d1b-421">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="e8d1b-421">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e8d1b-422">Crear un archivo de formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e8d1b-422">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="e8d1b-423">Usar un archivo de formato para importar datos en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e8d1b-423">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="e8d1b-424">Usar un archivo de formato para omitir una columna de tabla &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e8d1b-424">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="e8d1b-425">Usar un archivo de formato para omitir un campo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e8d1b-425">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="e8d1b-426">Usar un archivo de formato para asignar columnas de tabla a campos de un archivo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e8d1b-426">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="e8d1b-427">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="e8d1b-427">Related Content</span></span>  
 <span data-ttu-id="e8d1b-428">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e8d1b-428">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d1b-429">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8d1b-429">See Also</span></span>  
 <span data-ttu-id="e8d1b-430">[Importar y exportar datos en bloque &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e8d1b-430">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="e8d1b-431">[Tipos de datos &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e8d1b-431">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="e8d1b-432">[Archivos de formato no XML &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e8d1b-432">[Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="e8d1b-433">Archivos de formato para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e8d1b-433">Format Files for Importing or Exporting Data &#40;SQL Server&#41;</span></span>](format-files-for-importing-or-exporting-data-sql-server.md)  
  
  
