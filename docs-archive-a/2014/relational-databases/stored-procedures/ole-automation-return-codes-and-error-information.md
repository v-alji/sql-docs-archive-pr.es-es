---
title: Códigos de retorno e información de error de automatización OLE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: conceptual
helpviewer_keywords:
- return codes [SQL Server]
- OLE Automation [SQL Server], return codes
- OLE Automation [SQL Server], errors
ms.assetid: 9696fb05-e9e8-4836-b359-d4de0be0eeb2
author: stevestein
ms.author: sstein
ms.openlocfilehash: aecdbaedca42b7456dbdbda0407760959e546f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678155"
---
# <a name="ole-automation-return-codes-and-error-information"></a><span data-ttu-id="8b9f1-102">Códigos de retorno e información de error de OLE Automation</span><span class="sxs-lookup"><span data-stu-id="8b9f1-102">OLE Automation Return Codes and Error Information</span></span>
  <span data-ttu-id="8b9f1-103">Los procedimientos almacenados del sistema de OLE Automation devuelven un código de retorno `int` que es el HRESULT devuelto por la operación de OLE Automation subyacente.</span><span class="sxs-lookup"><span data-stu-id="8b9f1-103">The OLE Automation system stored procedures return an `int` return code that is the HRESULT returned by the underlying OLE Automation operation.</span></span> <span data-ttu-id="8b9f1-104">Un HRESULT con el valor 0 indica que la operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8b9f1-104">An HRESULT of 0 indicates success.</span></span> <span data-ttu-id="8b9f1-105">Un valor de HRESULT distinto de cero es un código de error OLE con formato hexadecimal 0x800*nnnnn*, pero cuando se devuelve como un `int` valor en un código de retorno de un procedimiento almacenado, HRESULT tiene el formato 214*nnnnnnn*.</span><span class="sxs-lookup"><span data-stu-id="8b9f1-105">A nonzero HRESULT is an OLE error code of the hexadecimal form 0x800*nnnnn*, but when returned as an `int` value in a stored procedure return code, HRESULT has the form 214*nnnnnnn*.</span></span>  
  
 <span data-ttu-id="8b9f1-106">Por ejemplo, pasar un nombre de objeto no válido (SQLDMO. XYZZY) en sp_OACreate hace que el procedimiento devuelva un `int` HRESULT de 2147221005, que se 0x800401f3 en hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="8b9f1-106">For example, passing an invalid object name (SQLDMO.Xyzzy) to sp_OACreate causes the procedure to return an `int` HRESULT of 2147221005, which is 0x800401f3 in hexadecimal.</span></span>  
  
 <span data-ttu-id="8b9f1-107">Puede utilizar `CONVERT(binary(4), @hresult)` para convertir un HRESULT `int` en un valor `binary`.</span><span class="sxs-lookup"><span data-stu-id="8b9f1-107">You can use `CONVERT(binary(4), @hresult)` to convert an `int` HRESULT to a `binary` value.</span></span> <span data-ttu-id="8b9f1-108">Sin embargo, el uso de `CONVERT(char(10), CONVERT(binary(4), @hresult))` da como resultado una cadena ilegible, porque cada byte de HRESULT se convierte en un carácter ASCII.</span><span class="sxs-lookup"><span data-stu-id="8b9f1-108">However, using `CONVERT(char(10), CONVERT(binary(4), @hresult))` results in an unreadable string, because each byte of the HRESULT is converted to a single ASCII character.</span></span> <span data-ttu-id="8b9f1-109">Puede usar el siguiente procedimiento almacenado HexToChar de ejemplo para convertir un `int` valor HRESULT en un `char` valor que contenga una cadena hexadecimal legible.</span><span class="sxs-lookup"><span data-stu-id="8b9f1-109">You can use the following sample HexToChar stored procedure to convert an `int` HRESULT to a `char` value that contains a readable hexadecimal string.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF EXISTS(SELECT name FROM sys.objects  
          WHERE name = N'dbo.sp_HexToChar')  
    DROP PROCEDURE HexToChar;  
GO  
CREATE PROCEDURE dbo.sp_HexToChar  
    @BinValue varbinary(255),  
    @HexCharValue nvarchar(255) OUTPUT  
AS  
    DECLARE @CharValue nvarchar(255);  
    DECLARE @Position int;  
    DECLARE @Length int;  
    DECLARE @HexString nchar(16);  
    SELECT @CharValue = N'0x';  
    SELECT @Position = 1;  
    SELECT @Length = DATALENGTH(@BinValue);  
    SELECT @HexString = N'0123456789ABCDEF';  
    WHILE (@Position <= @Length)  
    BEGIN  
        DECLARE @TempInt int;  
        DECLARE @FirstInt int;  
        DECLARE @SecondInt int;  
        SELECT @TempInt = CONVERT(int, SUBSTRING(@BinValue,@Position,1));  
        SELECT @FirstInt = FLOOR(@TempInt/16);  
        SELECT @SecondInt = @TempInt - (@FirstInt*16);  
        SELECT @CharValue = @CharValue +  
            SUBSTRING(@HexString, @FirstInt+1, 1) +  
            SUBSTRING(@HexString, @SecondInt+1, 1);  
        SELECT @Position = @Position + 1;  
    END  
    SELECT @HexCharValue = @CharValue;  
GO  
DECLARE @BinVariable varbinary(35);  
DECLARE @CharValue nvarchar(35);  
  
SET @BinVariable = 123456;  
  
EXECUTE dbo.sp_HexToChar  
    @binvalue = @BinVariable,  
    @HexCharValue = @CharValue OUTPUT;  
  
SELECT @BinVariable AS BinaryValue,  
    @CharValue AS CharacterRep;  
GO  
```  
  
 <span data-ttu-id="8b9f1-110">Puede usar el siguiente ejemplo de procedimiento almacenado, **sp_displayoaerrorinfo**, para mostrar información de errores de OLE Automation cuando alguno de los procedimientos de OLE Automation devuelva un código de retorno HRESULT distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="8b9f1-110">You can use the following sample stored procedure, **sp_displayoaerrorinfo** to display OLE Automation error information when one of the OLE Automation procedures returns a nonzero HRESULT return code.</span></span> <span data-ttu-id="8b9f1-111">Este procedimiento almacenado de ejemplo utiliza `HexToChar` .</span><span class="sxs-lookup"><span data-stu-id="8b9f1-111">This sample stored procedure uses `HexToChar`.</span></span>  
  
```  
CREATE PROCEDURE dbo.sp_DisplayOAErrorInfo  
    @Object int,  
    @HResult int  
AS  
    DECLARE @Output nvarchar(255);  
    DECLARE @HRHex nchar(10);  
    DECLARE @HR int;  
    DECLARE @Source nvarchar(255);  
    DECLARE @Description nvarchar(255);  
    PRINT N'OLE Automation Error Information';  
    EXEC HexToChar @HResult, @HRHex OUT;  
    SELECT @Output = N'  HRESULT: ' + @HRHex;  
    PRINT @Output;  
    EXEC @HR = sp_OAGetErrorInfo  
        @Object,  
        @Source OUT,  
        @Description OUT;  
    IF @HR = 0  
    BEGIN  
        SELECT @Output = N'  Source: ' + @Source;  
        PRINT @Output;  
        SELECT @Output = N'  Description: '  
               + @Description;  
        PRINT @Output;  
    END  
    ELSE  
    BEGIN  
       PRINT N' sp_OAGetErrorInfo failed.';  
       RETURN;  
    END  
GO  
```  
  
## <a name="related-content"></a><span data-ttu-id="8b9f1-112">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="8b9f1-112">Related Content</span></span>  
 [<span data-ttu-id="8b9f1-113">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8b9f1-113">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oageterrorinfo-transact-sql)  
  
  