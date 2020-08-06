---
title: Copia masiva de datos de texto e imagen | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], text data
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], image data
- ODBC, bulk copy operations
ms.assetid: 87155bfa-3a73-4158-9d4d-cb7435dac201
author: rothja
ms.author: jroth
ms.openlocfilehash: 9240fd0eb8c32ed39613824ea5a07764e277160c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677619"
---
# <a name="bulk-copying-text-and-image-data"></a><span data-ttu-id="b21ff-102">Copia masiva de datos de texto e imagen</span><span class="sxs-lookup"><span data-stu-id="b21ff-102">Bulk Copying Text and Image Data</span></span>
  <span data-ttu-id="b21ff-103">Los valores **Text**, **ntext**e **Image** grandes se copian de forma masiva mediante la función [bcp_moretext](../native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md) .</span><span class="sxs-lookup"><span data-stu-id="b21ff-103">Large **text**, **ntext**, and **image** values are bulk copied using the [bcp_moretext](../native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md) function.</span></span> <span data-ttu-id="b21ff-104">Codifique [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) para la columna **Text**, **ntext**o **Image** con un puntero *pdata* establecido en NULL que indica que los datos se proporcionarán con **bcp_moretext**.</span><span class="sxs-lookup"><span data-stu-id="b21ff-104">You code [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) for the **text**, **ntext**, or **image** column with a *pData* pointer set to NULL indicating the data will be provided with **bcp_moretext**.</span></span> <span data-ttu-id="b21ff-105">Es importante especificar la longitud exacta de los datos proporcionados para cada columna **Text**, **ntext**o **Image** en cada fila copiada de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="b21ff-105">It is important to specify the exact length of data supplied for each **text**, **ntext**,or **image** column in each bulk-copied row.</span></span> <span data-ttu-id="b21ff-106">Si la longitud de los datos de una columna es diferente de la especificada en [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md), use [bcp_collen](../native-client-odbc-extensions-bulk-copy-functions/bcp-collen.md) para establecer la longitud en el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="b21ff-106">If the length of the data for a column is different from the column length specified in [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md), use [bcp_collen](../native-client-odbc-extensions-bulk-copy-functions/bcp-collen.md) to set the length to the proper value.</span></span> <span data-ttu-id="b21ff-107">Un [bcp_sendrow](../native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md) envía todos los datos que no son de**texto**, no**ntext**ni de**imagen** ; a continuación, llame a **bcp_moretext** para enviar los datos **Text**, **ntext**o **Image** en unidades independientes.</span><span class="sxs-lookup"><span data-stu-id="b21ff-107">A [bcp_sendrow](../native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md) sends all the non-**text**, non-**ntext**, and non-**image** data; you then call **bcp_moretext** to send the **text**, **ntext**, or **image** data in separate units.</span></span> <span data-ttu-id="b21ff-108">Las funciones de copia masiva determinan que se han enviado todos los datos para la columna **Text**, **ntext**o **Image** actual cuando la suma de las longitudes de los datos enviados a través de **bcp_moretext** es igual a la longitud especificada en el **bcp_collen** o **bcp_bind**más reciente.</span><span class="sxs-lookup"><span data-stu-id="b21ff-108">Bulk copy functions determine that all data has been sent for the current **text**, **ntext**, or **image** column when the sum of the lengths of data sent through **bcp_moretext** equals the length specified in the latest **bcp_collen** or **bcp_bind**.</span></span>  
  
 <span data-ttu-id="b21ff-109">**bcp_moretext** no tiene ningún parámetro para identificar una columna.</span><span class="sxs-lookup"><span data-stu-id="b21ff-109">**bcp_moretext** has no parameter to identify a column.</span></span> <span data-ttu-id="b21ff-110">Cuando hay varias columnas **Text**, **ntext**o **image** en una fila, **bcp_moretext** funciona en las columnas **Text**, **ntext**o **Image** a partir de la columna que tiene el número ordinal más bajo y continúa con la columna con el número ordinal más alto.</span><span class="sxs-lookup"><span data-stu-id="b21ff-110">When there are multiple **text**, **ntext**, or **image** columns in a row, **bcp_moretext** operates on the **text**, **ntext**, or **image** columns starting with the column having the lowest ordinal number and proceeding to the column with the highest ordinal number.</span></span> <span data-ttu-id="b21ff-111">**bcp_moretext** va de una columna a la siguiente cuando la suma de las longitudes de los datos enviados es igual a la longitud especificada en el **bcp_collen** o **bcp_bind** más reciente de la columna actual.</span><span class="sxs-lookup"><span data-stu-id="b21ff-111">**bcp_moretext** goes from one column to the next when the sum of the lengths of data sent equals the length specified in the latest **bcp_collen** or **bcp_bind** for the current column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b21ff-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b21ff-112">See Also</span></span>  
 [<span data-ttu-id="b21ff-113">Realizar operaciones de copia masiva &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="b21ff-113">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](performing-bulk-copy-operations-odbc.md)  
  
  
