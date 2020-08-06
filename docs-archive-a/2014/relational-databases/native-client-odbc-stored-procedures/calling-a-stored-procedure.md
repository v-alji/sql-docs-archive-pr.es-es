---
title: Llamar a un procedimiento almacenado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- calling stored procedures
- ODBC, stored procedures
- stored procedures [ODBC], calling
- SQL Server Native Client ODBC driver, stored procedures
- ODBC CALL escape sequence
- escape sequences [SQL Server]
- CALL statement
ms.assetid: d13737f4-f641-45bf-b56c-523e2ffc080f
author: rothja
ms.author: jroth
ms.openlocfilehash: c6fa704e45e4e85b479ae8a40a3e567bea1ec5e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750857"
---
# <a name="calling-a-stored-procedure"></a><span data-ttu-id="d91bf-102">Llamar a un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="d91bf-102">Calling a Stored Procedure</span></span>
  <span data-ttu-id="d91bf-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client admite la secuencia de escape ODBC Call y la [!INCLUDE[tsql](../../includes/tsql-md.md)] instrucción [Execute](/sql/t-sql/language-elements/execute-transact-sql) para ejecutar procedimientos almacenados; la secuencia de escape ODBC Call es el método preferido.</span><span class="sxs-lookup"><span data-stu-id="d91bf-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports both the ODBC CALL escape sequence and the [!INCLUDE[tsql](../../includes/tsql-md.md)][EXECUTE](/sql/t-sql/language-elements/execute-transact-sql) statement for executing stored procedures; the ODBC CALL escape sequence is the preferred method.</span></span> <span data-ttu-id="d91bf-104">El uso de la sintaxis ODBC permite que una aplicación recupere los códigos de retorno de los procedimientos almacenados y el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client también está optimizado para usar un protocolo originalmente desarrollado para enviar llamadas a procedimiento remoto (RPC) entre equipos que ejecutan [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d91bf-104">Using ODBC syntax enables an application to retrieve the return codes of stored procedures and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is also optimized to use a protocol originally developed for sending remote procedure (RPC) calls between computers running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d91bf-105">Este protocolo RPC aumenta el rendimiento eliminando gran parte del procesamiento de parámetros y análisis de instrucciones que se realiza en el servidor.</span><span class="sxs-lookup"><span data-stu-id="d91bf-105">This RPC protocol increases performance by eliminating much of the parameter processing and statement parsing done on the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d91bf-106">Al llamar a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] procedimientos almacenados mediante parámetros con nombre con ODBC (para obtener más información, vea [enlazar parámetros por nombre (parámetros con nombre)](https://go.microsoft.com/fwlink/?LinkID=209721)), los nombres de los parámetros deben empezar por el \@ carácter ' '.</span><span class="sxs-lookup"><span data-stu-id="d91bf-106">When calling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures using named parameters with ODBC (for more information, see [Binding Parameters by Name (Named Parameters)](https://go.microsoft.com/fwlink/?LinkID=209721)), the parameter names must start with the '\@' character.</span></span> <span data-ttu-id="d91bf-107">Se trata de una restricción específica de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d91bf-107">This is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specific restriction.</span></span> <span data-ttu-id="d91bf-108">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client exige esta restricción de una manera más estricta que Microsoft Data Access Components (MDAC).</span><span class="sxs-lookup"><span data-stu-id="d91bf-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver enforces this restriction more strictly than the Microsoft Data Access Components (MDAC).</span></span>  
  
 <span data-ttu-id="d91bf-109">La secuencia de escape ODBC CALL para llamar a un procedimiento es:</span><span class="sxs-lookup"><span data-stu-id="d91bf-109">The ODBC CALL escape sequence for calling a procedure is:</span></span>  
  
 <span data-ttu-id="d91bf-110">{[**? =**]**Call**_procedure_name_[([*parámetro*] [**,**[*parámetro*]]...)]}</span><span class="sxs-lookup"><span data-stu-id="d91bf-110">{[**?=**]**call**_procedure_name_[([*parameter*][**,**[*parameter*]]...)]}</span></span>  
  
 <span data-ttu-id="d91bf-111">donde *procedure_name* especifica el nombre de un procedimiento y un *parámetro* especifica un parámetro de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d91bf-111">where *procedure_name* specifies the name of a procedure and *parameter* specifies a procedure parameter.</span></span> <span data-ttu-id="d91bf-112">Los parámetros con nombre solo se admiten en instrucciones que utilizan la secuencia de escape ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="d91bf-112">Named parameters are only supported in statements using the ODBC CALL escape sequence.</span></span>  
  
 <span data-ttu-id="d91bf-113">Un procedimiento puede tener cero o más parámetros.</span><span class="sxs-lookup"><span data-stu-id="d91bf-113">A procedure can have zero or more parameters.</span></span> <span data-ttu-id="d91bf-114">También puede devolver un valor (que se indica con el marcador de parámetro opcional ?= al inicio de la sintaxis).</span><span class="sxs-lookup"><span data-stu-id="d91bf-114">It can also return a value (as indicated by the optional parameter marker ?= at the start of the syntax).</span></span> <span data-ttu-id="d91bf-115">Si un parámetro es de entrada o de entrada/salida, puede ser un literal o un marcador de parámetro.</span><span class="sxs-lookup"><span data-stu-id="d91bf-115">If a parameter is an input or an input/output parameter, it can be a literal or a parameter marker.</span></span> <span data-ttu-id="d91bf-116">Si el parámetro es de salida, debe ser un marcador de parámetro porque se desconoce la salida.</span><span class="sxs-lookup"><span data-stu-id="d91bf-116">If the parameter is an output parameter, it must be a parameter marker because the output is unknown.</span></span> <span data-ttu-id="d91bf-117">Los marcadores de parámetros se deben enlazar con [SQLBindParameter](../../relational-databases/native-client-odbc-api/sqlbindparameter.md) antes de que se ejecute la instrucción de llamada de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d91bf-117">Parameter markers must be bound with [SQLBindParameter](../../relational-databases/native-client-odbc-api/sqlbindparameter.md) before the procedure call statement is executed.</span></span>  
  
 <span data-ttu-id="d91bf-118">Los parámetros de entrada y de entrada/salida pueden omitirse de las llamadas a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d91bf-118">Input and input/output parameters can be omitted from procedure calls.</span></span> <span data-ttu-id="d91bf-119">Si se llama a un procedimiento con paréntesis pero sin ningún parámetro, el controlador indica al origen de datos que use el valor predeterminado para el primer parámetro.</span><span class="sxs-lookup"><span data-stu-id="d91bf-119">If a procedure is called with parentheses but without any parameters, the driver instructs the data source to use the default value for the first parameter.</span></span> <span data-ttu-id="d91bf-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d91bf-120">For example:</span></span>  
  
 <span data-ttu-id="d91bf-121">{**call** _procedure_name_**()**}</span><span class="sxs-lookup"><span data-stu-id="d91bf-121">{**call** _procedure_name_**( )**}</span></span>  
  
 <span data-ttu-id="d91bf-122">Si el procedimiento no tiene ningún parámetro, puede producirse un error en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d91bf-122">If the procedure does not have any parameters, the procedure can fail.</span></span> <span data-ttu-id="d91bf-123">Si se llama a un procedimiento sin paréntesis, el controlador no envía ningún valor de parámetro.</span><span class="sxs-lookup"><span data-stu-id="d91bf-123">If a procedure is called without parentheses, the driver does not send any parameter values.</span></span> <span data-ttu-id="d91bf-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d91bf-124">For example:</span></span>  
  
 <span data-ttu-id="d91bf-125">{**call** _procedure_name_}</span><span class="sxs-lookup"><span data-stu-id="d91bf-125">{**call** _procedure_name_}</span></span>  
  
 <span data-ttu-id="d91bf-126">Pueden especificarse literales para los parámetros de entrada y de entrada/salida en llamadas a procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d91bf-126">Literals can be specified for input and input/output parameters in procedure calls.</span></span> <span data-ttu-id="d91bf-127">Por ejemplo, el procedimiento InsertOrder tiene cinco parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="d91bf-127">For example, the procedure InsertOrder has five input parameters.</span></span> <span data-ttu-id="d91bf-128">La siguiente llamada a InsertOrder omite el primer parámetro, proporciona un literal para el segundo parámetro y usa un marcador de parámetro para el tercero, cuarto y quinto parámetro.</span><span class="sxs-lookup"><span data-stu-id="d91bf-128">The following call to InsertOrder omits the first parameter, provides a literal for the second parameter, and uses a parameter marker for the third, fourth, and fifth parameters.</span></span> <span data-ttu-id="d91bf-129">(Los parámetros se numeran secuencialmente, comenzando por el valor 1.)</span><span class="sxs-lookup"><span data-stu-id="d91bf-129">(Parameters are numbered sequentially, beginning with a value of 1.)</span></span>  
  
```  
{call InsertOrder(, 10, ?, ?, ?)}  
```  
  
 <span data-ttu-id="d91bf-130">Tenga en cuenta que aunque se omita un parámetro, la coma que lo separa de los demás parámetros debe estar presente.</span><span class="sxs-lookup"><span data-stu-id="d91bf-130">Note that if a parameter is omitted, the comma delimiting it from other parameters must still appear.</span></span> <span data-ttu-id="d91bf-131">Si se omite un parámetro de entrada o de entrada/salida, el procedimiento usa el valor predeterminado del parámetro.</span><span class="sxs-lookup"><span data-stu-id="d91bf-131">If an input or input/output parameter is omitted, the procedure uses the default value of the parameter.</span></span> <span data-ttu-id="d91bf-132">Otras formas de especificar el valor predeterminado de un parámetro de entrada o de entrada/salida consisten en establecer el valor del búfer de longitud/indicador enlazado al parámetro en SQL_DEFAULT_PARAM, o bien, usar la palabra clave DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="d91bf-132">Other ways to specify the default value of an input or input/output parameter are to set the value of the length/indicator buffer bound to the parameter to SQL_DEFAULT_PARAM, or to use the DEFAULT keyword.</span></span>  
  
 <span data-ttu-id="d91bf-133">Si se omite un parámetro de entrada/salida, o si se proporciona un literal para el parámetro, el controlador descarta el valor de salida.</span><span class="sxs-lookup"><span data-stu-id="d91bf-133">If an input/output parameter is omitted, or if a literal is supplied for the parameter, the driver discards the output value.</span></span> <span data-ttu-id="d91bf-134">Del mismo modo, si se omite el marcador de parámetro para el valor devuelto de un procedimiento, el controlador descarta dicho valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="d91bf-134">Similarly, if the parameter marker for the return value of a procedure is omitted, the driver discards the return value.</span></span> <span data-ttu-id="d91bf-135">Finalmente, si una aplicación especifica un parámetro de valor devuelto para un procedimiento que no devuelve ningún valor, el controlador establece el valor del búfer de longitud/indicador enlazado al parámetro en SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="d91bf-135">Finally, if an application specifies a return value parameter for a procedure that does not return a value, the driver sets the value of the length/indicator buffer bound to the parameter to SQL_NULL_DATA.</span></span>  
  
## <a name="delimiters-in-call-statements"></a><span data-ttu-id="d91bf-136">Delimitadores en instrucciones CALL</span><span class="sxs-lookup"><span data-stu-id="d91bf-136">Delimiters in CALL Statements</span></span>  
 <span data-ttu-id="d91bf-137">De forma predeterminada, el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client también admite una opción de compatibilidad específica de la secuencia de escape ODBC { CALL }.</span><span class="sxs-lookup"><span data-stu-id="d91bf-137">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver by default also supports a compatibility option specific to the ODBC { CALL } escape sequence.</span></span> <span data-ttu-id="d91bf-138">El controlador acepta instrucciones CALL con un solo conjunto de comillas dobles que delimitan el nombre del procedimiento almacenado completo:</span><span class="sxs-lookup"><span data-stu-id="d91bf-138">The driver accepts CALL statements with only a single set of double quotation marks delimiting the entire stored procedure name:</span></span>  
  
```  
{ CALL "master.dbo.sp_who" }  
```  
  
 <span data-ttu-id="d91bf-139">De forma predeterminada, el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client también acepta instrucciones CALL que siguen las reglas ISO e incluyen cada identificador entre comillas dobles:</span><span class="sxs-lookup"><span data-stu-id="d91bf-139">By default the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver also accepts CALL statements that follow the ISO rules and enclose each identifier in double quotation marks:</span></span>  
  
```  
{ CALL "master"."dbo"."sp_who" }  
```  
  
 <span data-ttu-id="d91bf-140">No obstante, cuando el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client se ejecuta con la configuración predeterminada no admite el uso de cualquier forma de identificador entrecomillado con identificadores que contienen caracteres no especificados como legales en identificadores por el estándar ISO.</span><span class="sxs-lookup"><span data-stu-id="d91bf-140">When running with the default settings, however, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support using either form of quoted identifier with identifiers that contain characters not specified as legal in identifiers by the ISO standard.</span></span> <span data-ttu-id="d91bf-141">Por ejemplo, el controlador no puede tener acceso a un procedimiento almacenado denominado **"My. proc"** mediante una instrucción call con identificadores entre comillas:</span><span class="sxs-lookup"><span data-stu-id="d91bf-141">For example, the driver cannot access a stored procedure named **"My.Proc"** using a CALL statement with quoted identifiers:</span></span>  
  
```  
{ CALL "MyDB"."MyOwner"."My.Proc" }  
```  
  
 <span data-ttu-id="d91bf-142">El controlador interpreta esta instrucción como:</span><span class="sxs-lookup"><span data-stu-id="d91bf-142">This statement is interpreted by the driver as:</span></span>  
  
```  
{ CALL MyDB.MyOwner.My.Proc }  
```  
  
 <span data-ttu-id="d91bf-143">El servidor genera un error que indica que no existe un servidor vinculado denominado **MyDB** .</span><span class="sxs-lookup"><span data-stu-id="d91bf-143">The server raises an error that a linked server named **MyDB** does not exist.</span></span>  
  
 <span data-ttu-id="d91bf-144">Este problema no ocurre si se usan identificadores entre paréntesis; la instrucción se interpreta correctamente:</span><span class="sxs-lookup"><span data-stu-id="d91bf-144">The issue does not exist when using bracketed identifiers, this statement is interpreted correctly:</span></span>  
  
```  
{ CALL [MyDB].[MyOwner].[My.Table] }  
```  
  
## <a name="see-also"></a><span data-ttu-id="d91bf-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d91bf-145">See Also</span></span>  
 [<span data-ttu-id="d91bf-146">Ejecutar procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="d91bf-146">Running Stored Procedures</span></span>](../../relational-databases/native-client-odbc-stored-procedures/running-stored-procedures.md)  
  
  
