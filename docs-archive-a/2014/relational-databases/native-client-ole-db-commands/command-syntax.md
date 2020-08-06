---
title: Sintaxis de comandos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, commands
- commands [OLE DB]
- SQL Server Native Client OLE DB provider, stored procedures
- stored procedures [OLE DB], command syntax
ms.assetid: d463d3d7-e5cb-426d-8e92-aa29980356b6
author: rothja
ms.author: jroth
ms.openlocfilehash: da5ddb75a5c6fc10db031707b7d97ead71363e9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750806"
---
# <a name="command-syntax"></a><span data-ttu-id="c383f-102">Sintaxis de comandos</span><span class="sxs-lookup"><span data-stu-id="c383f-102">Command Syntax</span></span>
  <span data-ttu-id="c383f-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client reconoce la sintaxis de comandos especificada por la macro DBGUID_SQL.</span><span class="sxs-lookup"><span data-stu-id="c383f-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes command syntax specified by the DBGUID_SQL macro.</span></span> <span data-ttu-id="c383f-104">Para el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client, el especificador indica que una amalgama de ODBC SQL, ISO y [!INCLUDE[tsql](../../includes/tsql-md.md)] es una sintaxis válida.</span><span class="sxs-lookup"><span data-stu-id="c383f-104">For the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the specifier indicates that an amalgam of ODBC SQL, ISO, and [!INCLUDE[tsql](../../includes/tsql-md.md)] is valid syntax.</span></span> <span data-ttu-id="c383f-105">Por ejemplo, la siguiente instrucción SQL utiliza una secuencia de escape de ODBC SQL para especificar la función de cadena LCASE:</span><span class="sxs-lookup"><span data-stu-id="c383f-105">For example, the following SQL statement uses an ODBC SQL escape sequence to specify the LCASE string function:</span></span>  
  
```  
SELECT customerid={fn LCASE(CustomerID)} FROM Customers  
```  
  
 <span data-ttu-id="c383f-106">LCASE devuelve una cadena de caracteres, convirtiendo todos los caracteres en mayúscula en sus equivalentes en minúscula.</span><span class="sxs-lookup"><span data-stu-id="c383f-106">LCASE returns a character string, converting all uppercase characters to their lowercase equivalents.</span></span> <span data-ttu-id="c383f-107">La función de cadena ISO LOWER realiza la misma operación, de modo que la instrucción SQL siguiente es un equivalente ISO de la instrucción ODBC presentada anteriormente:</span><span class="sxs-lookup"><span data-stu-id="c383f-107">The ISO string function LOWER performs the same operation, so the following SQL statement is a ISO equivalent to the ODBC statement presented above:</span></span>  
  
```  
SELECT customerid=LOWER(CustomerID) FROM Customers  
```  
  
 <span data-ttu-id="c383f-108">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client procesa cualquier forma de la instrucción correctamente cuando se especifica como texto para un comando.</span><span class="sxs-lookup"><span data-stu-id="c383f-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider processes either form of the statement successfully when specified as text for a command.</span></span>  
  
## <a name="stored-procedures"></a><span data-ttu-id="c383f-109">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="c383f-109">Stored Procedures</span></span>  
 <span data-ttu-id="c383f-110">Al ejecutar un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] procedimiento almacenado mediante un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comando de proveedor de OLE DB de Native Client, utilice la secuencia de escape ODBC Call en el texto del comando.</span><span class="sxs-lookup"><span data-stu-id="c383f-110">When executing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider command, use the ODBC CALL escape sequence in the command text.</span></span> <span data-ttu-id="c383f-111">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]A continuación, el proveedor de OLE DB de Native Client utiliza el mecanismo de llamada a procedimiento remoto de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para optimizar el procesamiento de comandos.</span><span class="sxs-lookup"><span data-stu-id="c383f-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider then uses the remote procedure call mechanism of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to optimize command processing.</span></span> <span data-ttu-id="c383f-112">Por ejemplo, la instrucción SQL de ODBC siguiente es el texto de comando preferido sobre la forma [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c383f-112">For example, the following ODBC SQL statement is preferred command text over the [!INCLUDE[tsql](../../includes/tsql-md.md)] form:</span></span>  
  
-   <span data-ttu-id="c383f-113">ODBC SQL</span><span class="sxs-lookup"><span data-stu-id="c383f-113">ODBC SQL</span></span>  
  
    ```  
    {call SalesByCategory('Produce', '1995')}  
    ```  
  
-   <span data-ttu-id="c383f-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c383f-114">Transact-SQL</span></span>  
  
    ```  
    EXECUTE SalesByCategory 'Produce', '1995'  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c383f-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c383f-115">See Also</span></span>  
 [<span data-ttu-id="c383f-116">Comandos</span><span class="sxs-lookup"><span data-stu-id="c383f-116">Commands</span></span>](commands.md)  
  
  
