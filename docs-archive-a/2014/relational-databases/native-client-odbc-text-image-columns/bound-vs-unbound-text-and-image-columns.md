---
title: Columnas de imagen y texto enlazado frente a sin enlazar | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], image
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: ffd3442e-d880-46e9-b848-2365a09a2406
author: rothja
ms.author: jroth
ms.openlocfilehash: 20a91d26ac8c2d1201386cb19bde13b49a3dbada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750846"
---
# <a name="bound-vs-unbound-text-and-image-columns"></a><span data-ttu-id="71360-102">Texto delimitado frente a texto sin delimitar y columnas de imagen</span><span class="sxs-lookup"><span data-stu-id="71360-102">Bound vs. Unbound Text and Image Columns</span></span>
  <span data-ttu-id="71360-103">Cuando se utilizan cursores de servidor, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client está optimizado para no transmitir los datos para las columnas **Text**, **ntext**o **Image** sin enlazar en el momento en que se realiza el **SQLFetch** .</span><span class="sxs-lookup"><span data-stu-id="71360-103">When using server cursors, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is optimized to not transmit the data for unbound **text**, **ntext**, or **image** columns at the time **SQLFetch** is performed.</span></span> <span data-ttu-id="71360-104">Los datos **Text**, **ntext**o **Image** no se recuperan realmente del servidor hasta que la aplicación emite [SQLGetData](../native-client-odbc-api/sqlgetdata.md) para la columna.</span><span class="sxs-lookup"><span data-stu-id="71360-104">The **text**, **ntext**, or **image** data is not actually retrieved from the server until the application issues [SQLGetData](../native-client-odbc-api/sqlgetdata.md) for the column.</span></span>  
  
 <span data-ttu-id="71360-105">Se pueden escribir muchas aplicaciones para que no se muestren datos de **texto**, **ntext**o **Image** mientras un usuario simplemente se desplaza hacia arriba y hacia abajo en un cursor.</span><span class="sxs-lookup"><span data-stu-id="71360-105">Many applications can be written so that no **text**, **ntext**, or **image** data is displayed while a user is simply scrolling up and down in a cursor.</span></span> <span data-ttu-id="71360-106">Cuando un usuario selecciona una fila para obtener más detalles, la aplicación puede llamar a **SQLGetData** para recuperar los datos **Text**, **ntext**o **Image** .</span><span class="sxs-lookup"><span data-stu-id="71360-106">When a user selects a row to get more detail, the application can then call **SQLGetData** to retrieve the **text**, **ntext**, or **image** data.</span></span> <span data-ttu-id="71360-107">Esto evitará que se transmitan los datos **Text**, **ntext**o **Image** para cualquiera de las filas que el usuario no selecciona y, por tanto, puede evitar la transmisión de cantidades muy grandes de datos.</span><span class="sxs-lookup"><span data-stu-id="71360-107">This will prevent transmitting the **text**, **ntext**, or **image** data for any of the rows the user does not select, and can therefore prevent the transmission of very large amounts of data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71360-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71360-108">See Also</span></span>  
 <span data-ttu-id="71360-109">[Administrar columnas de texto e imagen](managing-text-and-image-columns.md) </span><span class="sxs-lookup"><span data-stu-id="71360-109">[Managing Text and Image Columns](managing-text-and-image-columns.md) </span></span>  
 [<span data-ttu-id="71360-110">Comportamientos de los cursores</span><span class="sxs-lookup"><span data-stu-id="71360-110">Cursor Behaviors</span></span>](../native-client-odbc-cursors/cursor-behaviors.md)  
  
  
