---
title: Modificaciones registradas frente a no registradas | Microsoft Docs
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
- data types [ODBC], image
- data types [ODBC], text
- logged vs. nonlogged modifications [SQL Server Native Client]
- columns [ODBC]
- ODBC data types, image columns
- nonlogged vs. logged modifications
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: 20aa5b27-4a2c-46e7-8356-beb0eebf4b7e
author: rothja
ms.author: jroth
ms.openlocfilehash: 8768acc75d18ea2236f0e9280e5d0c805e688107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750838"
---
# <a name="logged-vs-unlogged-modifications"></a><span data-ttu-id="dd015-102">Modificaciones registradas frente a modificaciones no registradas</span><span class="sxs-lookup"><span data-stu-id="dd015-102">Logged vs. Unlogged Modifications</span></span>
  <span data-ttu-id="dd015-103">Una aplicación puede solicitar que el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client no registre las modificaciones de **Text**, **ntext**e **Image** .</span><span class="sxs-lookup"><span data-stu-id="dd015-103">An application can request that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver not log **text**, **ntext**, and **image** modifications.</span></span> <span data-ttu-id="dd015-104">Sin embargo, se debe tener cautela con esta opción.</span><span class="sxs-lookup"><span data-stu-id="dd015-104">Care should be used with this option, however.</span></span> <span data-ttu-id="dd015-105">Solo se debe usar para aquellas situaciones en las que los datos **Text**, **ntext**o **Image** no son críticos y los propietarios de datos están dispuestos a deshacer la capacidad de recuperar datos para un mayor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="dd015-105">It should be used only for those situations where the **text**, **ntext**, or **image** data is not critical and data owners are willing to trade off the ability to recover data for higher performance.</span></span>  
  
 <span data-ttu-id="dd015-106">El registro de las modificaciones de **Text**, **ntext**e **Image** se controla mediante una llamada a [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) con el parámetro de *atributo* establecido en SQL_SOPT_SS_ TEXTPTR_LOGGING y *ValuePtr* establecido en SQL_TL_ON o SQL_TL_OFF.</span><span class="sxs-lookup"><span data-stu-id="dd015-106">The logging of **text**, **ntext**, and **image** modifications is controlled by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with the *Attribute* parameter set to SQL_SOPT_SS_ TEXTPTR_LOGGING and *ValuePtr* set to either SQL_TL_ON or SQL_TL_OFF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd015-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd015-107">See Also</span></span>  
 [<span data-ttu-id="dd015-108">Administrar columnas de texto e imagen</span><span class="sxs-lookup"><span data-stu-id="dd015-108">Managing Text and Image Columns</span></span>](managing-text-and-image-columns.md)  
  
  
