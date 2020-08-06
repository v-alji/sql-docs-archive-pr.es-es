---
title: Administrar columnas de texto e imagen | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- data types [ODBC], mapping
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: 7b543556-ff36-4d35-ac08-de96223d92cd
author: rothja
ms.author: jroth
ms.openlocfilehash: e9d7d5b0f48c68e8ac911f5e274c9afdb8cfe17d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750833"
---
# <a name="managing-text-and-image-columns"></a><span data-ttu-id="1ea4d-102">Administrar columnas de texto e imagen</span><span class="sxs-lookup"><span data-stu-id="1ea4d-102">Managing Text and Image Columns</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="1ea4d-103">los datos de tipo **Text**, **ntext**e **Image** (también denominados datos Long) son tipos de datos de cadenas binarias o de caracteres que pueden contener valores de datos demasiado grandes para caber en columnas **Char**, **VARCHAR**, **Binary**o **varbinary** .</span><span class="sxs-lookup"><span data-stu-id="1ea4d-103">**text**, **ntext**, and **image** data (also referred to as long data) are character or binary string data types that can hold data values too large to fit into **char**, **varchar**, **binary**, or **varbinary** columns.</span></span> <span data-ttu-id="1ea4d-104">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo de datos de **texto** se asigna al tipo de datos SQL_LONGVARCHAR ODBC; **ntext** se asigna a SQL_WLONGVARCHAR; y los mapas de **imagen** para SQL_LONGVARBINARY.</span><span class="sxs-lookup"><span data-stu-id="1ea4d-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **text** data type maps to the ODBC SQL_LONGVARCHAR data type; **ntext** maps to SQL_WLONGVARCHAR; and **image** maps to SQL_LONGVARBINARY.</span></span> <span data-ttu-id="1ea4d-105">Es posible que algunos elementos de datos, como documentos largos o mapas de bits grandes, resulten demasiado grandes para poder almacenarlos correctamente en la memoria.</span><span class="sxs-lookup"><span data-stu-id="1ea4d-105">Some data items, such as long documents or large bitmaps, may be too large to store reasonably in memory.</span></span> <span data-ttu-id="1ea4d-106">Para recuperar datos largos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en partes secuenciales, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client permite que una aplicación llame a [SQLGetData](../native-client-odbc-api/sqlgetdata.md).</span><span class="sxs-lookup"><span data-stu-id="1ea4d-106">To retrieve long data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in sequential parts, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver enables an application to call [SQLGetData](../native-client-odbc-api/sqlgetdata.md).</span></span> <span data-ttu-id="1ea4d-107">Para enviar datos largos en partes secuenciales, la aplicación puede llamar a [SQLPutData](../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="1ea4d-107">To send long data in sequential parts, the application can call [SQLPutData](../native-client-odbc-api/sqlputdata.md).</span></span> <span data-ttu-id="1ea4d-108">Los parámetros para los que se envían datos durante la ejecución se conocen como parámetros de datos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="1ea4d-108">Parameters for which data is sent at execution time are known as data-at-execution parameters.</span></span>  
  
 <span data-ttu-id="1ea4d-109">En realidad, una aplicación puede escribir o recuperar cualquier tipo de datos (no solo datos largos) con **SQLPutData** o **SQLGetData**, aunque solo los datos de **caracteres** y **binarios** se pueden enviar o recuperar en partes.</span><span class="sxs-lookup"><span data-stu-id="1ea4d-109">An application can actually write or retrieve any type of data (not just long data) with **SQLPutData** or **SQLGetData**, although only **character** and **binary** data can be sent or retrieved in parts.</span></span> <span data-ttu-id="1ea4d-110">Sin embargo, si los datos son lo suficientemente pequeños como para caber en un solo búfer, generalmente no hay ningún motivo para usar **SQLPutData** o **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="1ea4d-110">However, if the data is small enough to fit in a single buffer, there is generally no reason to use **SQLPutData** or **SQLGetData**.</span></span> <span data-ttu-id="1ea4d-111">Resulta mucho más fácil enlazar el búfer único al parámetro o columna.</span><span class="sxs-lookup"><span data-stu-id="1ea4d-111">It is much easier to bind the single buffer to the parameter or column.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ea4d-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1ea4d-112">In This Section</span></span>  
  
-   [<span data-ttu-id="1ea4d-113">Texto delimitado frente a texto sin delimitar y columnas de imagen</span><span class="sxs-lookup"><span data-stu-id="1ea4d-113">Bound vs. Unbound Text and Image Columns</span></span>](bound-vs-unbound-text-and-image-columns.md)  
  
-   [<span data-ttu-id="1ea4d-114">Modificaciones registradas frente a modificaciones no registradas</span><span class="sxs-lookup"><span data-stu-id="1ea4d-114">Logged vs. Unlogged Modifications</span></span>](logged-vs-unlogged-modifications.md)  
  
-   [<span data-ttu-id="1ea4d-115">Datos en ejecución y columnas de tipo text, ntext o image</span><span class="sxs-lookup"><span data-stu-id="1ea4d-115">Data-at-Execution and Text, ntext, or Image Columns</span></span>](data-at-execution-and-text-ntext-or-image-columns.md)  
  
## <a name="see-also"></a><span data-ttu-id="1ea4d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ea4d-116">See Also</span></span>  
 [<span data-ttu-id="1ea4d-117">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="1ea4d-117">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
