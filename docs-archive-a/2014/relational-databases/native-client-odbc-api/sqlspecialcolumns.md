---
title: SQLSpecialColumns | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLSpecialColumns function
ms.assetid: dffe02ed-8f79-4c9a-af34-98130bbe5462
author: rothja
ms.author: jroth
ms.openlocfilehash: c36ff73606e95ed7ee5e713b81acf7c177a42563
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672953"
---
# <a name="sqlspecialcolumns"></a><span data-ttu-id="59f04-102">SQLSpecialColumns</span><span class="sxs-lookup"><span data-stu-id="59f04-102">SQLSpecialColumns</span></span>
  <span data-ttu-id="59f04-103">Cuando se solicitan identificadores de fila (*IdentifierType* SQL_BEST_ROWID), **SQLSpecialColumns** devuelve un conjunto de resultados vacío (ninguna fila de datos) para cualquier ámbito solicitado distinto de SQL_SCOPE_CURROW.</span><span class="sxs-lookup"><span data-stu-id="59f04-103">When requesting row identifiers (*IdentifierType* SQL_BEST_ROWID), **SQLSpecialColumns** returns an empty result set (no data rows) for any requested scope other than SQL_SCOPE_CURROW.</span></span> <span data-ttu-id="59f04-104">El conjunto de resultados generado indica que las columnas solamente son válidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="59f04-104">The generated result set indicates that the columns are only valid within this scope.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="59f04-105">no admite pseudocolumnas para identificadores.</span><span class="sxs-lookup"><span data-stu-id="59f04-105">does not support pseudocolumns for identifiers.</span></span> <span data-ttu-id="59f04-106">El conjunto de resultados de **SQLSpecialColumns** identificará todas las columnas como SQL_PC_NOT_PSEUDO.</span><span class="sxs-lookup"><span data-stu-id="59f04-106">The **SQLSpecialColumns** result set will identify all columns as SQL_PC_NOT_PSEUDO.</span></span>  
  
 <span data-ttu-id="59f04-107">**SQLSpecialColumns** se puede ejecutar en un cursor estático.</span><span class="sxs-lookup"><span data-stu-id="59f04-107">**SQLSpecialColumns** can be executed on a static cursor.</span></span> <span data-ttu-id="59f04-108">Si se intenta ejecutar **SQLSpecialColumns** en un cursor actualizable (dinámico o controlado por conjunto de claves), devuelve SQL_SUCCESS_WITH_INFO para indicar que el tipo de cursor ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="59f04-108">An attempt to execute **SQLSpecialColumns** on an updatable (keyset-driven or dynamic) returns SQL_SUCCESS_WITH_INFO indicating the cursor type has been changed.</span></span>  
  
## <a name="sqlspecialcolumns-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="59f04-109">SQLSpecialColumns admite características mejoradas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="59f04-109">SQLSpecialColumns Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="59f04-110">Para obtener información sobre los valores devueltos para las columnas DATA_TYPE, TYPE_NAME, COLUMN_SIZE, BUFFER_LENGTH y DECIMAL_DIGTS para tipos de fecha y hora, vea [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="59f04-110">For information about the values returned for the columns DATA_TYPE, TYPE_NAME, COLUMN_SIZE, BUFFER_LENGTH, and DECIMAL_DIGTS for date/time types, see [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span></span>  
  
 <span data-ttu-id="59f04-111">Para obtener más información general, consulte [mejoras de fecha y hora &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="59f04-111">For more general information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlspecialcolumns-support-for-large-clr-udts"></a><span data-ttu-id="59f04-112">Compatibilidad con SQLSpecialColumns para el UDT CLR grandes</span><span class="sxs-lookup"><span data-stu-id="59f04-112">SQLSpecialColumns Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="59f04-113">**SQLSpecialColumns** admite tipos definidos por el usuario (UDT) CLR grandes.</span><span class="sxs-lookup"><span data-stu-id="59f04-113">**SQLSpecialColumns** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="59f04-114">Para obtener más información, vea [tipos CLR grandes definidos por el usuario &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="59f04-114">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59f04-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59f04-115">See Also</span></span>  
 <span data-ttu-id="59f04-116">[SQLSpecialColumns función)](https://go.microsoft.com/fwlink/?LinkId=59371) </span><span class="sxs-lookup"><span data-stu-id="59f04-116">[SQLSpecialColumns Function](https://go.microsoft.com/fwlink/?LinkId=59371) </span></span>  
 [<span data-ttu-id="59f04-117">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="59f04-117">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
