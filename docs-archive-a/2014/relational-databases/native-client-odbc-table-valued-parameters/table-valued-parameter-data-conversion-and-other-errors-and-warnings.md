---
title: Conversión de datos de parámetros con valores de tabla y otros errores y advertencias | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), data conversion
- table-valued parameters (ODBC), error messages
ms.assetid: edd45234-59dc-4338-94fc-330e820cc248
author: rothja
ms.author: jroth
ms.openlocfilehash: 45b9ba7f91b54548e096bbe47da6e01ba562f59d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662861"
---
# <a name="table-valued-parameter-data-conversion-and-other-errors-and-warnings"></a><span data-ttu-id="8fcaa-102">Conversión de datos de parámetros con valores de tabla y otros errores y advertencias</span><span class="sxs-lookup"><span data-stu-id="8fcaa-102">Table-Valued Parameter Data Conversion and Other Errors and Warnings</span></span>
  <span data-ttu-id="8fcaa-103">Los valores de columna de parámetro con valores de tabla se pueden convertir entre tipos de cliente y de servidor de la misma manera que otros valores de parámetro y columna.</span><span class="sxs-lookup"><span data-stu-id="8fcaa-103">Table-valued parameter column values can be converted between client and server data types in the same way as other column and parameter values.</span></span> <span data-ttu-id="8fcaa-104">Sin embargo, dado que un parámetro con valores de tabla puede contener varias columnas y filas, es importante poder identificar el valor real donde se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="8fcaa-104">But because a table-valued parameter can contain multiple columns and multiple rows, it is important to be able to identify the actual value where the error occurred.</span></span>  
  
 <span data-ttu-id="8fcaa-105">Cuando se detecta un error o una advertencia en una columna de parámetro con valores de tabla, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client genera un registro de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="8fcaa-105">When an error or warning is detected in a table-valued parameter column, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will generate a diagnostic record.</span></span> <span data-ttu-id="8fcaa-106">El mensaje de error contendrá el número de parámetro del parámetro con valores de tabla, más el ordinal de la columna y el número de fila.</span><span class="sxs-lookup"><span data-stu-id="8fcaa-106">The error message will contain the parameter number of the table-valued parameter, plus the column ordinal and row number.</span></span> <span data-ttu-id="8fcaa-107">Una aplicación también puede utilizar los campos de diagnóstico SQL_DIAG_SS_TABLE_COLUMN_NUMBER y SQL_DIAG_SS_TABLE_ROW_NUMBER dentro de registros de diagnóstico para determinar qué valores están asociados a errores y advertencias.</span><span class="sxs-lookup"><span data-stu-id="8fcaa-107">An application can also use the diagnostic fields SQL_DIAG_SS_TABLE_COLUMN_NUMBER and SQL_DIAG_SS_TABLE_ROW_NUMBER within diagnostic records to determine which values are associated with errors and warnings.</span></span> <span data-ttu-id="8fcaa-108">Estos campos de diagnóstico están disponibles en [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8fcaa-108">These diagnostic fields are available in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions.</span></span>  
  
 <span data-ttu-id="8fcaa-109">Los componentes de mensaje y SQLSTATE de registros de diagnóstico cumplen los comportamientos de ODBC existentes en todos los demás aspectos.</span><span class="sxs-lookup"><span data-stu-id="8fcaa-109">The SQLSTATE and message components of diagnostic records will conform to existing ODBC behavior in all other respects.</span></span> <span data-ttu-id="8fcaa-110">Es decir, a excepción de la información de identificación de parámetros, filas y columnas, los mensajes de error tienen los mismos valores para los parámetros con valores de tabla que para los parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="8fcaa-110">That is, except for the parameter, row, and column identification information, error messages have the same values for table-valued parameters as they would for non-table-valued parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fcaa-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8fcaa-111">See Also</span></span>  
 [<span data-ttu-id="8fcaa-112">Parámetros con valores de tabla &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="8fcaa-112">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
