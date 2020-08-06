---
title: Codificar y descodificar identificadores de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: bb9fe0d3-e432-42d3-b324-64dc908b544a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 88e7ebbc81d9c3cb91b1bf678075c5b5d0884890
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744732"
---
# <a name="encode-and-decode-sql-server-identifiers"></a><span data-ttu-id="11518-102">Codificar y descodificar identificadores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="11518-102">Encode and Decode SQL Server Identifiers</span></span>
  <span data-ttu-id="11518-103">Los identificadores delimitados de SQL Server a veces contienen caracteres no admitidos en las rutas de acceso de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11518-103">SQL Server delimited identifiers sometimes contain characters not supported in Windows PowerShell paths.</span></span> <span data-ttu-id="11518-104">Estos caracteres se pueden especificar codificando sus valores hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="11518-104">These characters can be specified by encoding their hexadecimal values.</span></span>  
  
1.  <span data-ttu-id="11518-105">**Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="11518-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="11518-106">**Para procesar los caracteres especiales:**  [Codificar un identificador](#EncodeIdent), [Descodificar un identificador](#DecodeIdent)</span><span class="sxs-lookup"><span data-stu-id="11518-106">**To process special characters:**  [Encoding an Identifier](#EncodeIdent), [Decoding an Identifier](#DecodeIdent)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="11518-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="11518-107">Before You Begin</span></span>  
 <span data-ttu-id="11518-108">Los caracteres que no se admiten en los nombres de ruta de acceso de Windows PowerShell se pueden representar, o codificar, como el carácter "%" seguido del valor hexadecimal del patrón de bits que representa el carácter, como en " **%** XX".</span><span class="sxs-lookup"><span data-stu-id="11518-108">Characters that are not supported in Windows PowerShell path names can be represented, or encoded, as the "%" character followed by the hexadecimal value for the bit pattern that represents the character, as in "**%** xx".</span></span> <span data-ttu-id="11518-109">La codificación siempre se puede usar para controlar los caracteres que no se admiten en las rutas de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11518-109">Encoding can always be used to handle characters that are not supported in Windows PowerShell paths.</span></span>  
  
 <span data-ttu-id="11518-110">El cmdlet **Encode-SqlName** toma como entrada un identificador de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="11518-110">The **Encode-SqlName** cmdlet takes as input a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifier.</span></span> <span data-ttu-id="11518-111">Genera una cadena con todos los caracteres que no son admitidos por el lenguaje de Windows PowerShell codificados con "%xx".</span><span class="sxs-lookup"><span data-stu-id="11518-111">It outputs a string with all the characters that are not supported by the Windows PowerShell language encoded with "%xx".</span></span> <span data-ttu-id="11518-112">El cmdlet **Decode-SqlName** toma como entrada un identificador de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] codificado y devuelve el identificador original.</span><span class="sxs-lookup"><span data-stu-id="11518-112">The **Decode-SqlName** cmdlet takes as input an encoded [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifier and returns the original identifier.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="11518-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="11518-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="11518-114">Los cmdlets de `Encode-Sqlname` y de `Decode-Sqlname` solo codifican o descodifican caracteres que se permiten en los identificadores delimitados de SQL Server, pero no solo se admiten en las rutas de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11518-114">The `Encode-Sqlname` and `Decode-Sqlname` cmdlets only encode or decode the characters that are allowed in SQL Server delimited identifiers, but are not supported in PowerShell paths.</span></span> <span data-ttu-id="11518-115">Estos son los caracteres codificados por **Encode-SqlName** y descodificados por **Decode-SqlName**:</span><span class="sxs-lookup"><span data-stu-id="11518-115">These are the characters encoded by **Encode-SqlName** and decoded by **Decode-SqlName**:</span></span>  
  
|||||||||||||  
|-|-|-|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="11518-116">**Carácter**</span><span class="sxs-lookup"><span data-stu-id="11518-116">**Character**</span></span>|\ |/|<span data-ttu-id="11518-117">:</span><span class="sxs-lookup"><span data-stu-id="11518-117">:</span></span>|%|\<|>|*|<span data-ttu-id="11518-118">?</span><span class="sxs-lookup"><span data-stu-id="11518-118">?</span></span>|<span data-ttu-id="11518-119">[</span><span class="sxs-lookup"><span data-stu-id="11518-119">[</span></span>|<span data-ttu-id="11518-120">]</span><span class="sxs-lookup"><span data-stu-id="11518-120">]</span></span>|<span data-ttu-id="11518-121">&#124;</span><span class="sxs-lookup"><span data-stu-id="11518-121">&#124;</span></span>|  
|<span data-ttu-id="11518-122">**Codificación hexadecimal**</span><span class="sxs-lookup"><span data-stu-id="11518-122">**Hexadecimal Encoding**</span></span>|<span data-ttu-id="11518-123">%5C</span><span class="sxs-lookup"><span data-stu-id="11518-123">%5C</span></span>|<span data-ttu-id="11518-124">%2F</span><span class="sxs-lookup"><span data-stu-id="11518-124">%2F</span></span>|<span data-ttu-id="11518-125">%3A</span><span class="sxs-lookup"><span data-stu-id="11518-125">%3A</span></span>|<span data-ttu-id="11518-126">%25</span><span class="sxs-lookup"><span data-stu-id="11518-126">%25</span></span>|<span data-ttu-id="11518-127">%3C</span><span class="sxs-lookup"><span data-stu-id="11518-127">%3C</span></span>|<span data-ttu-id="11518-128">%3E</span><span class="sxs-lookup"><span data-stu-id="11518-128">%3E</span></span>|<span data-ttu-id="11518-129">%2A</span><span class="sxs-lookup"><span data-stu-id="11518-129">%2A</span></span>|<span data-ttu-id="11518-130">%3F</span><span class="sxs-lookup"><span data-stu-id="11518-130">%3F</span></span>|<span data-ttu-id="11518-131">%5B</span><span class="sxs-lookup"><span data-stu-id="11518-131">%5B</span></span>|<span data-ttu-id="11518-132">%5D</span><span class="sxs-lookup"><span data-stu-id="11518-132">%5D</span></span>|<span data-ttu-id="11518-133">%7C</span><span class="sxs-lookup"><span data-stu-id="11518-133">%7C</span></span>|  
  
##  <a name="encoding-an-identifier"></a><a name="EncodeIdent"></a> <span data-ttu-id="11518-134">Codificar un identificador</span><span class="sxs-lookup"><span data-stu-id="11518-134">Encoding an Identifier</span></span>  
 <span data-ttu-id="11518-135">**Para codificar un identificador de SQL Server en una ruta de acceso de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="11518-135">**To encode a SQL Server identifier in a PowerShell path**</span></span>  
  
-   <span data-ttu-id="11518-136">Use uno de los dos métodos para codificar un identificador de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="11518-136">Use one of two methods to encode a SQL Server identifier:</span></span>  
  
    -   <span data-ttu-id="11518-137">Especifique el código hexadecimal para el carácter no compatible mediante la sintaxis %XX, donde el código hexadecimal es XX.</span><span class="sxs-lookup"><span data-stu-id="11518-137">Specify the hexadecimal code for the unsupported character using the syntax %XX, where XX is the hexadecimal code.</span></span>  
  
    -   <span data-ttu-id="11518-138">Pase el identificador como una cadena entrecomillada al cmdlet `Encode-Sqlname`</span><span class="sxs-lookup"><span data-stu-id="11518-138">Pass the identifier as a quoted string to the `Encode-Sqlname` cmdlet</span></span>  
  
### <a name="examples-encoding"></a><span data-ttu-id="11518-139">Ejemplos (codificación)</span><span class="sxs-lookup"><span data-stu-id="11518-139">Examples (Encoding)</span></span>  
 <span data-ttu-id="11518-140">Este ejemplo especifica la versión codificada del carácter (%3A) ":":</span><span class="sxs-lookup"><span data-stu-id="11518-140">This example specifies the encoded version of the ":" character (%3A):</span></span>  
  
```  
Set-Location Table%3ATest  
```  
  
 <span data-ttu-id="11518-141">También puede usar **Encode-SqlName** para compilar un nombre admitido por Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="11518-141">Alternatively, you can use **Encode-SqlName** to build a name supported by Windows PowerShell:</span></span>  
  
```powershell
Set-Location (Encode-SqlName "Table:Test")  
```  
  
##  <a name="decoding-an-identifier"></a><a name="DecodeIdent"></a> <span data-ttu-id="11518-142">Descodificar un identificador</span><span class="sxs-lookup"><span data-stu-id="11518-142">Decoding an Identifier</span></span>  
 <span data-ttu-id="11518-143">**Descodificar un identificador de SQL Server de una ruta de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="11518-143">**To decode a SQL Server identifier from a PowerShell path**</span></span>  
  
 <span data-ttu-id="11518-144">Use el cmdlet `Decode-Sqlname` para reemplazar las codificaciones hexadecimales con caracteres representados por la codificación.</span><span class="sxs-lookup"><span data-stu-id="11518-144">Use the `Decode-Sqlname` cmdlet to replace the hexadecimal encodings with the characters represented by the encoding.</span></span>  
  
### <a name="examples-decoding"></a><span data-ttu-id="11518-145">Ejemplos (descodificación)</span><span class="sxs-lookup"><span data-stu-id="11518-145">Examples (Decoding)</span></span>  
 <span data-ttu-id="11518-146">Este ejemplo devuelve “Table:Test”:</span><span class="sxs-lookup"><span data-stu-id="11518-146">This example returns "Table:Test":</span></span>  
  
```powershell
Decode-SqlName "Table%3ATest"  
```  
  
## <a name="see-also"></a><span data-ttu-id="11518-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11518-147">See Also</span></span>  
 <span data-ttu-id="11518-148">[SQL Server identificadores en PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="11518-148">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="11518-149">[Proveedor de SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="11518-149">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="11518-150">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="11518-150">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
