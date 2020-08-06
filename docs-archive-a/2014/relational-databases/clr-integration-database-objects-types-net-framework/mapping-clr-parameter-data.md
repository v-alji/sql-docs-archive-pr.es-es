---
title: Asignar datos de parámetros CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- SqlBinary data type
- SqlInt16 data type
- SqlMoney data type
- SqlString data type
- SqlSingle data type
- data types [CLR integration]
- SqlInt64 data type
- SqlDateTime data type
- SqlXml data type
- SqlBoolean data type
- SqlDecimal data type
- SqlBytes data type
- mapping data types [CLR integration]
- SqlChars data type
- SqlInt32 data type
ms.assetid: 89b43ee9-b9ad-4281-a4bf-c7c8d116daa2
author: rothja
ms.author: jroth
ms.openlocfilehash: 7025c5180eac793534961af63df9ac701c95c03f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751177"
---
# <a name="mapping-clr-parameter-data"></a><span data-ttu-id="27558-102">Asignar datos de parámetros CLR</span><span class="sxs-lookup"><span data-stu-id="27558-102">Mapping CLR Parameter Data</span></span>
  <span data-ttu-id="27558-103">En la tabla siguiente se enumeran los [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de datos, sus equivalentes en el Common Language Runtime (CLR) para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el `System.Data.SqlTypes` espacio de nombres y sus equivalentes de CLR nativos en el [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="27558-103">The following table lists [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, their equivalents in the common language runtime (CLR) for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the `System.Data.SqlTypes` namespace, and their native CLR equivalents in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="27558-104">**Tipos de datos de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="27558-104">**SQL Server data type**</span></span>|<span data-ttu-id="27558-105">Tipo (en System.Data.SqlTypes o Microsoft.SqlServer.Types)</span><span class="sxs-lookup"><span data-stu-id="27558-105">Type (in System.Data.SqlTypes or Microsoft.SqlServer.Types)</span></span>|<span data-ttu-id="27558-106">**Tipo de datos CLR (.NET Framework)**</span><span class="sxs-lookup"><span data-stu-id="27558-106">**CLR data type (.NET Framework)**</span></span>|  
|`bigint`|`SqlInt64`|<span data-ttu-id="27558-107">**Int64, que admite valores NULL\<Int64>**</span><span class="sxs-lookup"><span data-stu-id="27558-107">**Int64, Nullable\<Int64>**</span></span>|  
|`binary`|`SqlBytes, SqlBinary`|`Byte[]`|  
|`bit`|`SqlBoolean`|<span data-ttu-id="27558-108">**Booleano, acepta valores NULL\<Boolean>**</span><span class="sxs-lookup"><span data-stu-id="27558-108">**Boolean, Nullable\<Boolean>**</span></span>|  
|`char`|<span data-ttu-id="27558-109">None</span><span class="sxs-lookup"><span data-stu-id="27558-109">None</span></span>|<span data-ttu-id="27558-110">None</span><span class="sxs-lookup"><span data-stu-id="27558-110">None</span></span>|  
|`cursor`|<span data-ttu-id="27558-111">None</span><span class="sxs-lookup"><span data-stu-id="27558-111">None</span></span>|<span data-ttu-id="27558-112">None</span><span class="sxs-lookup"><span data-stu-id="27558-112">None</span></span>|  
|`date`|`SqlDateTime`|<span data-ttu-id="27558-113">**DateTime, que admite valores NULL\<DateTime>**</span><span class="sxs-lookup"><span data-stu-id="27558-113">**DateTime, Nullable\<DateTime>**</span></span>|  
|`datetime`|`SqlDateTime`|<span data-ttu-id="27558-114">**DateTime, que admite valores NULL\<DateTime>**</span><span class="sxs-lookup"><span data-stu-id="27558-114">**DateTime, Nullable\<DateTime>**</span></span>|  
|`datetime2`|<span data-ttu-id="27558-115">None</span><span class="sxs-lookup"><span data-stu-id="27558-115">None</span></span>|<span data-ttu-id="27558-116">**DateTime, que admite valores NULL\<DateTime>**</span><span class="sxs-lookup"><span data-stu-id="27558-116">**DateTime, Nullable\<DateTime>**</span></span>|  
|`DATETIMEOFFSET`|`None`|<span data-ttu-id="27558-117">**DateTimeOffset, que admite valores NULL\<DateTimeOffset>**</span><span class="sxs-lookup"><span data-stu-id="27558-117">**DateTimeOffset, Nullable\<DateTimeOffset>**</span></span>|  
|`decimal`|`SqlDecimal`|<span data-ttu-id="27558-118">**Decimal, admite valores NULL\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="27558-118">**Decimal, Nullable\<Decimal>**</span></span>|  
|`float`|`SqlDouble`|<span data-ttu-id="27558-119">**Double, que admite valores NULL\<Double>**</span><span class="sxs-lookup"><span data-stu-id="27558-119">**Double, Nullable\<Double>**</span></span>|  
|`geography`|`SqlGeography`<br /><br /> <span data-ttu-id="27558-120">`SqlGeography`se define en Microsoft.SqlServer.Types.dll, que se instala con SQL Server y se puede descargar desde el [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Feature Pack](https://www.microsoft.com/download/details.aspx?id=53164).</span><span class="sxs-lookup"><span data-stu-id="27558-120">`SqlGeography` is defined in Microsoft.SqlServer.Types.dll, which is installed with SQL Server and can be downloaded from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][feature pack](https://www.microsoft.com/download/details.aspx?id=53164).</span></span>|<span data-ttu-id="27558-121">None</span><span class="sxs-lookup"><span data-stu-id="27558-121">None</span></span>|  
|`geometry`|`SqlGeometry`<br /><br /> <span data-ttu-id="27558-122">`SqlGeometry`se define en Microsoft.SqlServer.Types.dll, que se instala con SQL Server y se puede descargar desde el [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Feature Pack](https://www.microsoft.com/download/details.aspx?id=53164).</span><span class="sxs-lookup"><span data-stu-id="27558-122">`SqlGeometry` is defined in Microsoft.SqlServer.Types.dll, which is installed with SQL Server and can be downloaded from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][feature pack](https://www.microsoft.com/download/details.aspx?id=53164).</span></span>|<span data-ttu-id="27558-123">None</span><span class="sxs-lookup"><span data-stu-id="27558-123">None</span></span>|  
|`hierarchyid`|`SqlHierarchyId`<br /><br /> <span data-ttu-id="27558-124">`SqlHierarchyId`se define en Microsoft.SqlServer.Types.dll, que se instala con SQL Server y se puede descargar desde el [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Feature Pack](https://www.microsoft.com/download/details.aspx?id=53164).</span><span class="sxs-lookup"><span data-stu-id="27558-124">`SqlHierarchyId` is defined in Microsoft.SqlServer.Types.dll, which is installed with SQL Server and can be downloaded from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][feature pack](https://www.microsoft.com/download/details.aspx?id=53164).</span></span>|<span data-ttu-id="27558-125">None</span><span class="sxs-lookup"><span data-stu-id="27558-125">None</span></span>|  
|`image`|<span data-ttu-id="27558-126">None</span><span class="sxs-lookup"><span data-stu-id="27558-126">None</span></span>|<span data-ttu-id="27558-127">None</span><span class="sxs-lookup"><span data-stu-id="27558-127">None</span></span>|  
|`int`|`SqlInt32`|<span data-ttu-id="27558-128">**Int32, que admite valores NULL\<Int32>**</span><span class="sxs-lookup"><span data-stu-id="27558-128">**Int32, Nullable\<Int32>**</span></span>|  
|`money`|`SqlMoney`|<span data-ttu-id="27558-129">**Decimal, admite valores NULL\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="27558-129">**Decimal, Nullable\<Decimal>**</span></span>|  
|`nchar`|`SqlChars, SqlString`|`String, Char[]`|  
|`ntext`|<span data-ttu-id="27558-130">None</span><span class="sxs-lookup"><span data-stu-id="27558-130">None</span></span>|<span data-ttu-id="27558-131">None</span><span class="sxs-lookup"><span data-stu-id="27558-131">None</span></span>|  
|`numeric`|`SqlDecimal`|<span data-ttu-id="27558-132">**Decimal, admite valores NULL\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="27558-132">**Decimal, Nullable\<Decimal>**</span></span>|  
|`nvarchar`|`SqlChars, SqlString`<br /><br /> <span data-ttu-id="27558-133">`SQLChars` es más adecuado para la transferencia de datos y el acceso a los mismos, mientras que `SQLString` es mejor para realizar operaciones de cadena.</span><span class="sxs-lookup"><span data-stu-id="27558-133">`SQLChars` is a better match for data transfer and access, and `SQLString` is a better match for performing String operations.</span></span>|`String, Char[]`|  
|`nvarchar(1), nchar(1)`|`SqlChars, SqlString`|<span data-ttu-id="27558-134">**Char, String, Char [], que admite valores NULL\<char>**</span><span class="sxs-lookup"><span data-stu-id="27558-134">**Char, String, Char[], Nullable\<char>**</span></span>|  
|`real`|<span data-ttu-id="27558-135">`SqlSingle` (el intervalo de `SqlSingle`, sin embargo, es mayor que `real`)</span><span class="sxs-lookup"><span data-stu-id="27558-135">`SqlSingle` (the range of `SqlSingle`, however, is larger than `real`)</span></span>|<span data-ttu-id="27558-136">**Single, que admite valores NULL\<Single>**</span><span class="sxs-lookup"><span data-stu-id="27558-136">**Single, Nullable\<Single>**</span></span>|  
|`rowversion`|<span data-ttu-id="27558-137">None</span><span class="sxs-lookup"><span data-stu-id="27558-137">None</span></span>|`Byte[]`|  
|`smallint`|`SqlInt16`|<span data-ttu-id="27558-138">**Int16, que admite valores NULL\<Int16>**</span><span class="sxs-lookup"><span data-stu-id="27558-138">**Int16, Nullable\<Int16>**</span></span>|  
|`smallmoney`|`SqlMoney`|<span data-ttu-id="27558-139">**Decimal, admite valores NULL\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="27558-139">**Decimal, Nullable\<Decimal>**</span></span>|  
|`sql_variant`|<span data-ttu-id="27558-140">None</span><span class="sxs-lookup"><span data-stu-id="27558-140">None</span></span>|`Object`|  
|`table`|<span data-ttu-id="27558-141">None</span><span class="sxs-lookup"><span data-stu-id="27558-141">None</span></span>|<span data-ttu-id="27558-142">None</span><span class="sxs-lookup"><span data-stu-id="27558-142">None</span></span>|  
|`text`|<span data-ttu-id="27558-143">None</span><span class="sxs-lookup"><span data-stu-id="27558-143">None</span></span>|<span data-ttu-id="27558-144">None</span><span class="sxs-lookup"><span data-stu-id="27558-144">None</span></span>|  
|`time`|<span data-ttu-id="27558-145">None</span><span class="sxs-lookup"><span data-stu-id="27558-145">None</span></span>|<span data-ttu-id="27558-146">**TimeSpan, que admite valores NULL\<TimeSpan>**</span><span class="sxs-lookup"><span data-stu-id="27558-146">**TimeSpan, Nullable\<TimeSpan>**</span></span>|  
|`timestamp`|<span data-ttu-id="27558-147">None</span><span class="sxs-lookup"><span data-stu-id="27558-147">None</span></span>|<span data-ttu-id="27558-148">None</span><span class="sxs-lookup"><span data-stu-id="27558-148">None</span></span>|  
|`tinyint`|`SqlByte`|<span data-ttu-id="27558-149">**Byte, que admite valores NULL\<Byte>**</span><span class="sxs-lookup"><span data-stu-id="27558-149">**Byte, Nullable\<Byte>**</span></span>|  
|`uniqueidentifier`|`SqlGuid`|<span data-ttu-id="27558-150">**GUID, que admite valores NULL\<Guid>**</span><span class="sxs-lookup"><span data-stu-id="27558-150">**Guid, Nullable\<Guid>**</span></span>|  
|`User-defined type(UDT)`|<span data-ttu-id="27558-151">None</span><span class="sxs-lookup"><span data-stu-id="27558-151">None</span></span>|<span data-ttu-id="27558-152">La misma clase que está enlazada al tipo definido por el usuario en el mismo ensamblado o en un ensamblado dependiente.</span><span class="sxs-lookup"><span data-stu-id="27558-152">The same class that is bound to the user-defined type in the same assembly or a dependent assembly.</span></span>|  
|<span data-ttu-id="27558-153">**varbinary**</span><span class="sxs-lookup"><span data-stu-id="27558-153">**varbinary**</span></span>|`SqlBytes, SqlBinary`|`Byte[]`|  
|`varbinary(1), binary(1)`|`SqlBytes, SqlBinary`|<span data-ttu-id="27558-154">**byte, Byte [], que admite valores NULL\<byte>**</span><span class="sxs-lookup"><span data-stu-id="27558-154">**byte, Byte[], Nullable\<byte>**</span></span>|  
|`varchar`|<span data-ttu-id="27558-155">None</span><span class="sxs-lookup"><span data-stu-id="27558-155">None</span></span>|<span data-ttu-id="27558-156">None</span><span class="sxs-lookup"><span data-stu-id="27558-156">None</span></span>|  
|`xml`|`SqlXml`|<span data-ttu-id="27558-157">None</span><span class="sxs-lookup"><span data-stu-id="27558-157">None</span></span>|  
  
## <a name="automatic-data-type-conversion-with-out-parameters"></a><span data-ttu-id="27558-158">Conversión automática de tipos de datos con parámetros OUT</span><span class="sxs-lookup"><span data-stu-id="27558-158">Automatic Data Type Conversion with Out Parameters</span></span>  
 <span data-ttu-id="27558-159">Un método CLR puede devolver información al código o programa de llamada marcando un parámetro de entrada con el modificador `out` (Microsoft Visual C#) o `<Out()> ByRef` (Microsoft Visual Basic). Si el parámetro de entrada es un tipo de datos CLR del espacio de nombres `System.Data.SqlTypes` y el programa de llamada especifica su tipo de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] equivalente como parámetro de entrada, se produce una conversión de tipos automáticamente cuando el método CLR devuelve el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="27558-159">A CLR method can return information to the calling code or program by marking an input parameter with the `out` modifier (Microsoft Visual C#) or `<Out()> ByRef` (Microsoft Visual Basic) If the input parameter is a CLR data type in the `System.Data.SqlTypes` namespace, and the calling program specifies its equivalent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type as the input parameter, a type conversion occurs automatically when the CLR method returns the data type.</span></span>  
  
 <span data-ttu-id="27558-160">Por ejemplo, el siguiente procedimiento almacenado CLR tiene un parámetro de entrada de tipos de datos CLR `SqlInt32` que se marca con `out` (C#) o `<Out()> ByRef` (Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="27558-160">For example, the following CLR stored procedure has an input parameter of `SqlInt32` CLR data type that is marked with `out` (C#) or `<Out()> ByRef` (Visual Basic):</span></span>  
  
```csharp  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void PriceSum(out SqlInt32 value)  
{ ... }  
```  
  
```vb  
<Microsoft.SqlServer.Server.SqlProcedure> _  
Public Shared Sub PriceSum( <Out()> ByRef value As SqlInt32)  
...  
End Sub  
```  
  
 <span data-ttu-id="27558-161">Una vez generado y creado el ensamblado en la base de datos, el procedimiento almacenado se crea en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con el siguiente Transact-SQL, que especifica un tipo de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de `int` como parámetro OUTPUT:</span><span class="sxs-lookup"><span data-stu-id="27558-161">After the assembly is built and created in the database, the stored procedure is created in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the following Transact-SQL, which specifies a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of `int` as an OUTPUT parameter:</span></span>  
  
```  
CREATE PROCEDURE PriceSum (@sum int OUTPUT)  
AS EXTERNAL NAME TestStoredProc.StoredProcedures.PriceSum  
```  
  
 <span data-ttu-id="27558-162">Cuando se llama al procedimiento almacenado CLR, el tipo de datos `SqlInt32` se convierte automáticamente en un tipo de datos `int` y se devuelve al programa que hace la llamada.</span><span class="sxs-lookup"><span data-stu-id="27558-162">When the CLR stored procedure is called, the `SqlInt32` data type is automatically converted to an `int` data type, and returned to the calling program.</span></span>  
  
 <span data-ttu-id="27558-163">Pero no todos los tipos de datos CLR se pueden convertir automáticamente en sus tipos de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] equivalentes mediante un parámetro OUT.</span><span class="sxs-lookup"><span data-stu-id="27558-163">Not all CLR data types can be automatically converted to their equivalent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types through an out parameter, however.</span></span> <span data-ttu-id="27558-164">En la tabla siguiente se enumeran estas excepciones.</span><span class="sxs-lookup"><span data-stu-id="27558-164">The following table lists these exceptions.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="27558-165">**Tipo de datos CLR (SQL Server)**</span><span class="sxs-lookup"><span data-stu-id="27558-165">**CLR data type (SQL Server)**</span></span>|<span data-ttu-id="27558-166">**Tipos de datos de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="27558-166">**SQL Server data type**</span></span>|  
|`Decimal`|<span data-ttu-id="27558-167">SMALLMONEY</span><span class="sxs-lookup"><span data-stu-id="27558-167">smallmoney</span></span>|  
|`SqlMoney`|<span data-ttu-id="27558-168">SMALLMONEY</span><span class="sxs-lookup"><span data-stu-id="27558-168">smallmoney</span></span>|  
|`Decimal`|<span data-ttu-id="27558-169">money</span><span class="sxs-lookup"><span data-stu-id="27558-169">money</span></span>|  
|`DateTime`|<span data-ttu-id="27558-170">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="27558-170">smalldatetime</span></span>|  
|`SQLDateTime`|<span data-ttu-id="27558-171">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="27558-171">smalldatetime</span></span>|  
  
## <a name="change-history"></a><span data-ttu-id="27558-172">Historial de cambios</span><span class="sxs-lookup"><span data-stu-id="27558-172">Change History</span></span>  
  
|<span data-ttu-id="27558-173">Contenido actualizado</span><span class="sxs-lookup"><span data-stu-id="27558-173">Updated content</span></span>|  
|---------------------|  
|<span data-ttu-id="27558-174">Se han agregado los tipos `SqlGeography`, `SqlGeometry` y `SqlHierarchyId` a la tabla de asignación.</span><span class="sxs-lookup"><span data-stu-id="27558-174">Added `SqlGeography`, `SqlGeometry`, and `SqlHierarchyId` types to the mapping table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27558-175">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27558-175">See Also</span></span>  
 [<span data-ttu-id="27558-176">Tipos de datos de SQL Server en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="27558-176">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
