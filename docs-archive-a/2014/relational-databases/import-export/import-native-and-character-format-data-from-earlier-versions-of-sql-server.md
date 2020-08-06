---
title: Importar datos con formato nativo y de caracteres de versiones anteriores de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- earlier versions [SQL Server], import and export data formats
- -V switch
- data formats [SQL Server], earlier versions
- previous versions [SQL Server], import and export data formats
ms.assetid: e644696f-9017-428e-a5b3-d445d1c630b3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 274c984d6ecec8af8f5bea27496450a45fc2f1df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675371"
---
# <a name="import-native-and-character-format-data-from-earlier-versions-of-sql-server"></a><span data-ttu-id="fa730-102">Importar datos con formato nativo y de caracteres de versiones anteriores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="fa730-102">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>
  <span data-ttu-id="fa730-103">En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]puede usar **bcp** para importar datos con formato nativo y de caracteres de [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]o [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] con el modificador **-V** .</span><span class="sxs-lookup"><span data-stu-id="fa730-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can use **bcp** to import native and character format data from [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] by using the **-V** switch.</span></span> <span data-ttu-id="fa730-104">El modificador **-V** hace que [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] use los tipos de datos de la versión anterior especificada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], y el formato del archivo de datos es el mismo que el de esa versión anterior.</span><span class="sxs-lookup"><span data-stu-id="fa730-104">The **-V** switch causes [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to use data types from the specified earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and the data file format are the same as the format in that earlier version.</span></span>  
  
 <span data-ttu-id="fa730-105">Para especificar una versión anterior de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para un archivo de datos, use el modificador **-V** con uno de los siguientes calificadores:</span><span class="sxs-lookup"><span data-stu-id="fa730-105">To specify an earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version for a data file, use the **-V** switch with one of the following qualifiers:</span></span>  
  
|<span data-ttu-id="fa730-106">Versión de SQL Server</span><span class="sxs-lookup"><span data-stu-id="fa730-106">SQL Server version</span></span>|<span data-ttu-id="fa730-107">Qualifier</span><span class="sxs-lookup"><span data-stu-id="fa730-107">Qualifier</span></span>|  
|------------------------|---------------|  
|[!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]|<span data-ttu-id="fa730-108">**-V80**</span><span class="sxs-lookup"><span data-stu-id="fa730-108">**-V80**</span></span>|  
|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|<span data-ttu-id="fa730-109">**-V90**</span><span class="sxs-lookup"><span data-stu-id="fa730-109">**-V90**</span></span>|  
|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|<span data-ttu-id="fa730-110">**-V100**</span><span class="sxs-lookup"><span data-stu-id="fa730-110">**-V100**</span></span>|  
|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]|<span data-ttu-id="fa730-111">**-V 110**</span><span class="sxs-lookup"><span data-stu-id="fa730-111">**-V 110**</span></span>|  
  
## <a name="interpretation-of-data-types"></a><span data-ttu-id="fa730-112">Interpretación de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="fa730-112">Interpretation of Data Types</span></span>  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="fa730-113">y versiones posteriores tienen compatibilidad para algunos nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="fa730-113">and later versions have support for some new types.</span></span> <span data-ttu-id="fa730-114">Si desea importar un tipo de datos nuevo en una versión anterior de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , debe almacenarlo en un formato que pueda ser leído por la versión anterior de los clientes **bcp** .</span><span class="sxs-lookup"><span data-stu-id="fa730-114">When you want to import a new data type into an earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version, the data type must be stored in a format that readable by the older **bcp** clients.</span></span> <span data-ttu-id="fa730-115">En la tabla siguiente se resume cómo se convierten los tipos de datos nuevos a efectos de compatibilidad con las versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa730-115">The following table summarizes how the new data types are converted for compatibility with the earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="fa730-116">Nuevos tipos de datos de SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="fa730-116">New data types in SQL Server 2005</span></span>|<span data-ttu-id="fa730-117">Tipos de datos compatibles de la versión 6*x*</span><span class="sxs-lookup"><span data-stu-id="fa730-117">Compatible data types in version 6*x*</span></span>|<span data-ttu-id="fa730-118">Tipos de datos compatibles de la versión 70</span><span class="sxs-lookup"><span data-stu-id="fa730-118">Compatible data types in version 70</span></span>|<span data-ttu-id="fa730-119">Tipos de datos compatibles de la versión 80</span><span class="sxs-lookup"><span data-stu-id="fa730-119">Compatible data types in version 80</span></span>|  
|---------------------------------------|-------------------------------------------|-----------------------------------------|-----------------------------------------|  
|`bigint`|`decimal`|`decimal`|*|  
|`sql_variant`|`text`|`nvarchar(4000)`|*|  
|`varchar(max)`|`text`|`text`|`text`|  
|`nvarchar(max)`|`ntext`|`ntext`|`ntext`|  
|`varbinary(max)`|`image`|`image`|`image`|  
|<span data-ttu-id="fa730-120">XML</span><span class="sxs-lookup"><span data-stu-id="fa730-120">XML</span></span>|`ntext`|`ntext`|`ntext`|  
|<span data-ttu-id="fa730-121">UDT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fa730-121">UDT<sup>1</sup></span></span>|`image`|`image`|`image`|  
  
 <span data-ttu-id="fa730-122">\*Este tipo es compatible de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="fa730-122">\* This type is natively supported.</span></span>  
  
 <span data-ttu-id="fa730-123"><sup>1</sup> UDT indica un tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="fa730-123"><sup>1</sup> UDT indicates a user defined type.</span></span>  
  
## <a name="exporting-using--v-80"></a><span data-ttu-id="fa730-124">Exportación mediante -V 80</span><span class="sxs-lookup"><span data-stu-id="fa730-124">Exporting using -V 80</span></span>  
 <span data-ttu-id="fa730-125">Cuando se exportan datos de forma masiva mediante el modificador **-V80** , los datos de,,, `nvarchar(max)` `varchar(max)` `varbinary(max)` XML y UDT en modo nativo se almacenan con un prefijo de 4 bytes, como `text` los datos de tipo, `image` y `ntext` , en lugar de con un prefijo de 8 bytes, que es el valor predeterminado para [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="fa730-125">When you bulk export data by using the **-V80** switch, `nvarchar(max)`, `varchar(max)`, `varbinary(max)`, XML, and UDT data in native mode are stored with a 4-byte prefix, like `text`, `image`, and `ntext` data, rather than with an 8-byte prefix, which is the default for [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span>  
  
## <a name="copying-date-values"></a><span data-ttu-id="fa730-126">Copiar valores de fecha</span><span class="sxs-lookup"><span data-stu-id="fa730-126">Copying Date Values</span></span>  
 <span data-ttu-id="fa730-127">**bcp** utiliza la API de copia masiva de ODBC.</span><span class="sxs-lookup"><span data-stu-id="fa730-127">**bcp** uses the ODBC bulk copy API.</span></span> <span data-ttu-id="fa730-128">Por tanto, para importar valores de fecha en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], **bcp** usa el formato de fecha ODBC (*yyyy-mm-dd hh:mm:ss*[ *.f...* ]).</span><span class="sxs-lookup"><span data-stu-id="fa730-128">Therefore, to import date values into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], **bcp** uses the ODBC date format (*yyyy-mm-dd hh:mm:ss*[*.f...*]).</span></span>  
  
 <span data-ttu-id="fa730-129">El comando **BCP** exporta los archivos de datos con formato de caracteres utilizando el formato predeterminado ODBC para `datetime` `smalldatetime` los valores y.</span><span class="sxs-lookup"><span data-stu-id="fa730-129">The **bcp** command exports character format data files using the ODBC default format for `datetime` and `smalldatetime` values.</span></span> <span data-ttu-id="fa730-130">Por ejemplo, una columna `datetime` que contiene la fecha `12 Aug 1998` se copia de forma masiva en un archivo de datos como la cadena de caracteres `1998-08-12 00:00:00.000`.</span><span class="sxs-lookup"><span data-stu-id="fa730-130">For example, a `datetime` column containing the date `12 Aug 1998` is bulk copied to a data file as the character string `1998-08-12 00:00:00.000`.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fa730-131">Al importar datos en un `smalldatetime` campo mediante **BCP**, asegúrese de que el valor de los segundos sea 00,000; de lo contrario, se producirá un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="fa730-131">When importing data into a `smalldatetime` field using **bcp**, be sure the value for seconds is 00.000; otherwise the operation will fail.</span></span> <span data-ttu-id="fa730-132">El tipo de datos `smalldatetime` contiene únicamente valores hasta el minuto más cercano.</span><span class="sxs-lookup"><span data-stu-id="fa730-132">The `smalldatetime` data type only holds values to the nearest minute.</span></span> <span data-ttu-id="fa730-133">BULK INSERT e INSERT ... SELECT \* FROM OPENROWSET(BULK...) no darán error en esta instancia, pero truncarán el valor de los segundos.</span><span class="sxs-lookup"><span data-stu-id="fa730-133">BULK INSERT and INSERT ... SELECT \* FROM OPENROWSET(BULK...) will not fail in this instance but will truncate the seconds value.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="fa730-134">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="fa730-134">Related Tasks</span></span>  
 <span data-ttu-id="fa730-135">**Para usar formatos de datos para la importación o exportación masivas**</span><span class="sxs-lookup"><span data-stu-id="fa730-135">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="fa730-136">Usar el formato de caracteres para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fa730-136">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="fa730-137">Usar el formato nativo para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fa730-137">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="fa730-138">Usar el formato de caracteres Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fa730-138">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="fa730-139">Usar el formato nativo Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fa730-139">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 
  
## <a name="see-also"></a><span data-ttu-id="fa730-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa730-140">See Also</span></span>  
 <span data-ttu-id="fa730-141">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="fa730-141">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="fa730-142">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa730-142">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="fa730-143">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa730-143">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="fa730-144">[Tipos de datos &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa730-144">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="fa730-145">[Compatibilidad con versiones anteriores del Motor de base de datos de SQL Server](../../database-engine/sql-server-database-engine-backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="fa730-145">[SQL Server Database Engine Backward Compatibility](../../database-engine/sql-server-database-engine-backward-compatibility.md) </span></span>  
 [<span data-ttu-id="fa730-146">CAST y CONVERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fa730-146">CAST and CONVERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cast-and-convert-transact-sql)  
  
  
