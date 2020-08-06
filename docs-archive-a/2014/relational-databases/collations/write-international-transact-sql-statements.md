---
title: Escribir instrucciones Transact-SQL internacionales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- writing international statements
- Transact-SQL international considerations
- international considerations [SQL Server], Transact-SQL
- Database Engine international considerations [SQL Server], Transact-SQL
- statements [SQL Server], international
- database international considerations [SQL Server], Transact-SQL
- dates [SQL Server], international considerations
ms.assetid: f0b10fee-27f7-45fe-aece-ccc3f63bdcdb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1888d1045e43e0a9839fd76a21c51500af63539a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677682"
---
# <a name="write-international-transact-sql-statements"></a><span data-ttu-id="941bc-102">Escribir instrucciones Transact-SQL internacionales</span><span class="sxs-lookup"><span data-stu-id="941bc-102">Write International Transact-SQL Statements</span></span>
  <span data-ttu-id="941bc-103">Las bases de datos y las aplicaciones de bases de datos que utilizan instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] obtendrán una mayor portabilidad de un idioma a otro, o admitirán varios idiomas, si se siguen estas directrices:</span><span class="sxs-lookup"><span data-stu-id="941bc-103">Databases and database applications that use [!INCLUDE[tsql](../../includes/tsql-md.md)] statements will become more portable from one language to another, or will support multiple languages, if the following guidelines are followed:</span></span>  
  
-   <span data-ttu-id="941bc-104">Reemplace todos los tipos de datos `char`, `varchar` y `text` con `nchar`, `nvarchar` y `nvarchar(max)` respectivamente.</span><span class="sxs-lookup"><span data-stu-id="941bc-104">Replace all uses of the `char`, `varchar`, and `text` data types with `nchar`, `nvarchar`, and `nvarchar(max)`.</span></span> <span data-ttu-id="941bc-105">De esta forma, se evita problemas de conversión de páginas de códigos.</span><span class="sxs-lookup"><span data-stu-id="941bc-105">By doing this, you do not have to consider code page conversion issues.</span></span> <span data-ttu-id="941bc-106">Para más información, consulte [Compatibilidad con la intercalación y Unicode](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="941bc-106">For more information, see [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
-   <span data-ttu-id="941bc-107">Cuando realice comparaciones y operaciones con los meses y días de la semana, utilice las partes numéricas de la fecha en lugar de cadenas de nombres.</span><span class="sxs-lookup"><span data-stu-id="941bc-107">When you perform month and day-of-week comparisons and operations, use the numeric date parts instead of the name strings.</span></span> <span data-ttu-id="941bc-108">Las distintas configuraciones de idioma devuelven nombres diferentes para los meses y los días de la semana.</span><span class="sxs-lookup"><span data-stu-id="941bc-108">Different language settings return different names for the months and weekdays.</span></span> <span data-ttu-id="941bc-109">Por ejemplo, DATENAME(MONTH,GETDATE()) devuelve May cuando el idioma está establecido en inglés de EE.UU. Mai cuando el idioma es alemán y mai cuando el idioma es francés.</span><span class="sxs-lookup"><span data-stu-id="941bc-109">For example, DATENAME(MONTH,GETDATE()) returns May when the language is set to U.S. English, returns Mai when the language is set to German, and returns mai when the language is set to French.</span></span> <span data-ttu-id="941bc-110">En su lugar, utilice una función como DATEPART que utiliza el número del mes en lugar del nombre.</span><span class="sxs-lookup"><span data-stu-id="941bc-110">Instead, use a function such as DATEPART that uses the number of the month instead of the name.</span></span> <span data-ttu-id="941bc-111">Utilice los nombres DATEPART cuando genere conjuntos de resultados que se van a mostrar al usuario ya que, generalmente, los nombres de fecha resultan más significativos que una representación numérica.</span><span class="sxs-lookup"><span data-stu-id="941bc-111">Use the DATEPART names when you build result sets to be displayed to a user, because the date names are frequently more meaningful than a numeric representation.</span></span> <span data-ttu-id="941bc-112">No codifique, sin embargo, ninguna lógica que dependa de que los nombres mostrados estén en un idioma determinado.</span><span class="sxs-lookup"><span data-stu-id="941bc-112">However, do not code any logic that depends on the displayed names being from a specific language.</span></span>  
  
-   <span data-ttu-id="941bc-113">Cuando especifique fechas en las comparaciones o como entrada de las instrucciones INSERT o UPDATE, utilice constantes que se interpretan igual en todas las configuraciones de idioma:</span><span class="sxs-lookup"><span data-stu-id="941bc-113">When you specify dates in comparisons or for input to INSERT or UPDATE statements, use constants that are interpreted the same way for all language settings:</span></span>  
  
    -   <span data-ttu-id="941bc-114">Las aplicaciones ADO, OLE DB y ODBC deben utilizar la siguiente marca de tiempo, fecha y cláusulas de escape de hora ODBC:</span><span class="sxs-lookup"><span data-stu-id="941bc-114">ADO, OLE DB, and ODBC applications should use the ODBC timestamp, date, and time escape clauses of:</span></span>  
  
         <span data-ttu-id="941bc-115">**{ts '** AAAA **-** _mm_ **-** _DDHH_**:**_mm_**:**_SS_[**.** _FFF_] **'}** por ejemplo: **{ts '** 1998 **-** 09 **-** 24 10 **:** 02 **:** 20 **'}**</span><span class="sxs-lookup"><span data-stu-id="941bc-115">**{ ts'** yyyy**-**_mm_**-**_ddhh_**:**_mm_**:**_ss_[**.**_fff_] **'}** such as: **{ ts'** 1998**-** 09**-** 24 10 **:** 02 **:** 20 **' }**</span></span>  
  
         <span data-ttu-id="941bc-116">**{ d'** _aaaa_ **-** _mm_ **-** _dd_ **'}** , como: **{ d'** 1998**-** 09**-** 24 **'}**</span><span class="sxs-lookup"><span data-stu-id="941bc-116">**{ d'** _yyyy_ **-** _mm_ **-** _dd_ **'}** such as: **{ d'** 1998**-** 09**-** 24 **'}**</span></span>  
  
         <span data-ttu-id="941bc-117">**{t '** _HH_ **:** _mm_ **:** _SS_ **'}** como: **{t '** 10:02:20 **'}**</span><span class="sxs-lookup"><span data-stu-id="941bc-117">**{ t'** _hh_ **:** _mm_ **:** _ss_ **'}** such as: **{ t'** 10:02:20 **'}**</span></span>  
  
    -   <span data-ttu-id="941bc-118">Las aplicaciones que utilizan otras API o desencadenadores, procedimientos almacenados y scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] deben utilizar las cadenas numéricas sin separar.</span><span class="sxs-lookup"><span data-stu-id="941bc-118">Applications that use other APIs, or [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, stored procedures, and triggers, should use the unseparated numeric strings.</span></span> <span data-ttu-id="941bc-119">Por ejemplo, *yyyymmdd* como en 19980924.</span><span class="sxs-lookup"><span data-stu-id="941bc-119">For example, *yyyymmdd* as 19980924.</span></span>  
  
    -   <span data-ttu-id="941bc-120">Las aplicaciones que usan otras API o [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, procedimientos almacenados y desencadenadores deben usar la instrucción Convert con un parámetro de estilo explícito para todas las conversiones entre los tipos de datos `time` , `date` , `smalldate` , `datetime` , **datetime2**y tipos de datos `datetimeoffset` y cadenas de caracteres.</span><span class="sxs-lookup"><span data-stu-id="941bc-120">Applications that use other APIs, or [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, stored procedures, and triggers should use the CONVERT statement with an explicit style parameter for all conversions between the `time`, `date`, `smalldate`, `datetime`, **datetime2**, and `datetimeoffset` data types and character string data types.</span></span> <span data-ttu-id="941bc-121">Por ejemplo, la siguiente instrucción se interpreta igual en todas las configuraciones de conexión de formato de fecha o de idioma:</span><span class="sxs-lookup"><span data-stu-id="941bc-121">For example, the following statement is interpreted in the same way for all language or date format connection settings:</span></span>  
  
        ```  
        SELECT *  
        FROM AdventureWorks2012.Sales.SalesOrderHeader  
        WHERE OrderDate = CONVERT(DATETIME, '20060719', 101)  
        ```  
  
         <span data-ttu-id="941bc-122">Para obtener más información, vea [CAST y CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="941bc-122">For more information, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
  
