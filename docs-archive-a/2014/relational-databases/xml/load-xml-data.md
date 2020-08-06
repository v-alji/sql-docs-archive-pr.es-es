---
title: Carga de datos XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML data [SQL Server], loading
- loading XML data
ms.assetid: d1741e8d-f44e-49ec-9f14-10208b5468a7
author: rothja
ms.author: jroth
ms.openlocfilehash: c48d1d6feccb7df9fec9801ee56abcab99884754
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746794"
---
# <a name="load-xml-data"></a><span data-ttu-id="23d16-102">Cargar datos XML</span><span class="sxs-lookup"><span data-stu-id="23d16-102">Load XML Data</span></span>
  <span data-ttu-id="23d16-103">Puede transferir los datos XML a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="23d16-103">You can transfer XML data into [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in several ways.</span></span> <span data-ttu-id="23d16-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="23d16-104">For example:</span></span>  
  
-   <span data-ttu-id="23d16-105">Si tiene datos en una columna [n]text o image en una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , puede importar la tabla mediante [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23d16-105">If you have your data in an [n]text or image column in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, you can import the table by using [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="23d16-106">Cambie el tipo de columna a XML mediante la instrucción ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="23d16-106">Change the column type to XML by using the ALTER TABLE statement.</span></span>  
  
-   <span data-ttu-id="23d16-107">Puede realizar una copia masiva de los datos desde otra base de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante bcp out y, después, hacer una inserción masiva de los datos en la versión posterior de la base de datos mediante bcp in.</span><span class="sxs-lookup"><span data-stu-id="23d16-107">You can bulk copy your data from another [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database by using bcp out, and then bulk insert the data into the later version database by using bcp in.</span></span>  
  
-   <span data-ttu-id="23d16-108">Si tiene datos en columnas relacionales de una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , cree una tabla nueva con una columna [n]text y, si lo desea, una columna de clave principal para disponer de un identificador de fila.</span><span class="sxs-lookup"><span data-stu-id="23d16-108">If you have data in relational columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, create a new table with an [n]text column and, optionally, a primary key column for a row identifier.</span></span> <span data-ttu-id="23d16-109">Use programación del lado cliente para recuperar el XML que se genera en el servidor con FOR XML y escribirlo en la columna `[n]text`.</span><span class="sxs-lookup"><span data-stu-id="23d16-109">Use client-side programming to retrieve the XML that is generated at the server with FOR XML and write it into the `[n]text` column.</span></span> <span data-ttu-id="23d16-110">A continuación, use las técnicas mencionadas previamente para transferir datos a una base de datos de una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="23d16-110">Then, use the previously mentioned techniques to transfer data to a later version database.</span></span> <span data-ttu-id="23d16-111">Puede optar por escribir el XML directamente en una columna XML en la base de datos de la versión posterior.</span><span class="sxs-lookup"><span data-stu-id="23d16-111">You can choose to write the XML into an XML column in the later version database directly.</span></span>  
  
## <a name="bulk-loading-xml-data"></a><span data-ttu-id="23d16-112">Carga masiva de datos XML</span><span class="sxs-lookup"><span data-stu-id="23d16-112">Bulk loading XML data</span></span>  
 <span data-ttu-id="23d16-113">Puede realizar una carga masiva de datos XML en el servidor mediante las funciones de carga masiva de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], como bcp.</span><span class="sxs-lookup"><span data-stu-id="23d16-113">You can bulk load XML data into the server by using the bulk loading capabilities of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as bcp.</span></span> <span data-ttu-id="23d16-114">OPENROWSET permite cargar datos en una columna XML desde archivos.</span><span class="sxs-lookup"><span data-stu-id="23d16-114">OPENROWSET allows you to load data into an XML column from files.</span></span> <span data-ttu-id="23d16-115">El siguiente ejemplo muestra esta función.</span><span class="sxs-lookup"><span data-stu-id="23d16-115">The following example illustrates this point.</span></span>  
  
##### <a name="example-loading-xml-from-files"></a><span data-ttu-id="23d16-116">Ejemplo: Carga de XML desde archivos</span><span class="sxs-lookup"><span data-stu-id="23d16-116">Example: Loading XML from Files</span></span>  
 <span data-ttu-id="23d16-117">Este ejemplo muestra cómo insertar una fila en la tabla T. El valor de la columna XML se carga desde el archivo C:\MyFile\xmlfile.xml como CLOB y se suministra el valor 10 a la columna de enteros.</span><span class="sxs-lookup"><span data-stu-id="23d16-117">This example shows how to insert a row in table T. The value of the XML column is loaded from file C:\MyFile\xmlfile.xml as CLOB, and the integer column is supplied the value 10.</span></span>  
  
```  
INSERT INTO T  
SELECT 10, xCol  
FROM    (SELECT *      
    FROM OPENROWSET (BULK 'C:\MyFile\xmlfile.xml', SINGLE_CLOB)   
 AS xCol) AS R(xCol)  
```  
  
## <a name="text-encoding"></a><span data-ttu-id="23d16-118">Codificación de texto</span><span class="sxs-lookup"><span data-stu-id="23d16-118">Text Encoding</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="23d16-119">almacena los datos XML en Unicode (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="23d16-119">stores XML data in Unicode (UTF-16).</span></span> <span data-ttu-id="23d16-120">Los datos XML recuperados del servidor se reciben con codificación UTF-16.</span><span class="sxs-lookup"><span data-stu-id="23d16-120">XML data retrieved from the server comes out in UTF-16 encoding.</span></span> <span data-ttu-id="23d16-121">Si desea otra codificación, tendrá que realizar la conversión necesaria en los datos recuperados.</span><span class="sxs-lookup"><span data-stu-id="23d16-121">If you want a different encoding, you have to perform the required conversion on the retrieved data.</span></span> <span data-ttu-id="23d16-122">En ocasiones, los datos XML pueden tener una codificación distinta.</span><span class="sxs-lookup"><span data-stu-id="23d16-122">Sometimes, the XML data may be in a different encoding.</span></span> <span data-ttu-id="23d16-123">Si éste es el caso, debe prestar atención al cargar los datos.</span><span class="sxs-lookup"><span data-stu-id="23d16-123">If it is, you have to use care during data loading.</span></span> <span data-ttu-id="23d16-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="23d16-124">For example:</span></span>  
  
-   <span data-ttu-id="23d16-125">Si el XML de texto es Unicode (UCS-2, UTF-16), puede asignarlo a una columna, una variable o un parámetro XML sin problemas.</span><span class="sxs-lookup"><span data-stu-id="23d16-125">If your text XML is in Unicode (UCS-2, UTF-16), you can assign it to an XML column, variable, or parameter  without any problems.</span></span>  
  
-   <span data-ttu-id="23d16-126">Si la codificación no es Unicode y está implícita, debido a la página de códigos original, la página de códigos de cadena de la base de datos debe coincidir o ser compatible con los puntos de código que desea cargar.</span><span class="sxs-lookup"><span data-stu-id="23d16-126">If the encoding is not Unicode and is implicit, because of the source code page, the string code page in the database should be the same as or compatible with the code points that you want to load.</span></span> <span data-ttu-id="23d16-127">Si es necesario, use COLLATE.</span><span class="sxs-lookup"><span data-stu-id="23d16-127">If required, use COLLATE.</span></span> <span data-ttu-id="23d16-128">Si no existe tal página de códigos de servidor, deberá agregar una declaración XML explícita con la codificación correcta.</span><span class="sxs-lookup"><span data-stu-id="23d16-128">If no such server code page exists, you have to add an explicit XML declaration with the correct encoding.</span></span>  
  
-   <span data-ttu-id="23d16-129">Para usar una codificación explícita, utilice el tipo `varbinary()`, que no tiene interacción con páginas de códigos, o un tipo de cadena de la página de códigos apropiada.</span><span class="sxs-lookup"><span data-stu-id="23d16-129">To use an explicit encoding, use either the `varbinary()` type, which has no interaction with code pages, or use a string type of the appropriate code page.</span></span> <span data-ttu-id="23d16-130">A continuación, asigne los datos a una columna, una variable o un parámetro XML.</span><span class="sxs-lookup"><span data-stu-id="23d16-130">Then, assign the data to an XML column, variable, or parameter.</span></span>  
  
### <a name="example-explicitly-specifying-an-encoding"></a><span data-ttu-id="23d16-131">Ejemplo: Especificación explícita de una codificación</span><span class="sxs-lookup"><span data-stu-id="23d16-131">Example: Explicitly Specifying an Encoding</span></span>  
 <span data-ttu-id="23d16-132">Suponga que tiene un documento XML, vcdoc, almacenado como `varchar(max)`, que no dispone de una declaración XML explícita.</span><span class="sxs-lookup"><span data-stu-id="23d16-132">Assume that you have an XML document, vcdoc, stored as `varchar(max)` that does not have an explicit XML declaration.</span></span> <span data-ttu-id="23d16-133">La instrucción siguiente agrega una declaración XML con la codificación "iso8859-1", concatena el documento XML, convierte el resultado a `varbinary(max)` de modo que se preserve la representación de bytes y, finalmente, lo convierte a XML.</span><span class="sxs-lookup"><span data-stu-id="23d16-133">The following statement adds an XML declaration with the encoding "iso8859-1", concatenates the XML document, casts the result to `varbinary(max)` so that the byte representation is preserved, and then finally casts it to XML.</span></span> <span data-ttu-id="23d16-134">De este modo, se habilita el procesador XML para analizar los datos según la codificación especificada "iso8859-1" y generar la representación UTF-16 correspondiente para los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="23d16-134">This enables the XML processor to parse the data according to the specified encoding "iso8859-1" and generate the corresponding UTF-16 representation for string values.</span></span>  
  
```  
SELECT CAST(   
CAST (('<?xml version="1.0" encoding="iso8859-1"?>'+ vcdoc) AS VARBINARY (MAX))   
 AS XML)  
```  
  
### <a name="string-encoding-incompatibilities"></a><span data-ttu-id="23d16-135">Incompatibilidades de codificación de cadenas</span><span class="sxs-lookup"><span data-stu-id="23d16-135">String Encoding Incompatibilities</span></span>  
 <span data-ttu-id="23d16-136">Si se copia y se pega XML como un literal de cadena en una ventana del Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], pueden producirse incompatibilidades de codificación de cadenas [N]VARCHAR.</span><span class="sxs-lookup"><span data-stu-id="23d16-136">If you copy and paste XML as a string literal into the Query Editor window in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you might experience [N]VARCHAR string encoding incompatibilities.</span></span> <span data-ttu-id="23d16-137">Esto dependerá de la codificación de la instancia XML.</span><span class="sxs-lookup"><span data-stu-id="23d16-137">This will depend on the encoding of your XML instance.</span></span> <span data-ttu-id="23d16-138">En muchos casos, es posible que se desee quitar la declaración XML.</span><span class="sxs-lookup"><span data-stu-id="23d16-138">In many cases, you may want to remove the XML declaration.</span></span> <span data-ttu-id="23d16-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="23d16-139">For example:</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
  <xsd:schema ...  
```  
  
 <span data-ttu-id="23d16-140">Debe incluirse una N a continuación para que la instancia XML sea una instancia de Unicode.</span><span class="sxs-lookup"><span data-stu-id="23d16-140">You should then include an N to make the XML instance an instance of Unicode.</span></span> <span data-ttu-id="23d16-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="23d16-141">For example:</span></span>  
  
```  
-- Assign XML instance to a variable.  
DECLARE @X XML  
SET @X = N'...'  
-- Insert XML instance into an xml type column.  
INSERT INTO T VALUES (N'...')  
-- Create an XML schema collection  
CREATE XML SCHEMA COLLECTION XMLCOLL1 AS N'<xsd:schema ... '  
```  
  
## <a name="see-also"></a><span data-ttu-id="23d16-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="23d16-142">See Also</span></span>  
 [<span data-ttu-id="23d16-143">Datos XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="23d16-143">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
