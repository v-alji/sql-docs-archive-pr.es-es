---
title: Usar la cláusula OUTPUT con OLE DB en SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 53deeb99-c088-4fde-844b-b2d91d6de1eb
author: rothja
ms.author: jroth
ms.openlocfilehash: a425ec6269040c72836571b8fa8b51bba4ed8c32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748750"
---
# <a name="using-the-output-clause-with-ole-db-in-sql-server-native-client"></a><span data-ttu-id="c90f3-102">Usar la cláusula OUTPUT con OLE DB en SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="c90f3-102">Using the OUTPUT Clause with OLE DB in SQL Server Native Client</span></span>
  <span data-ttu-id="c90f3-103">Si utiliza una cláusula OUTPUT en un comando INSERT, UPDATE, DELETE o MERGE, no estará disponible el recuento de filas afectadas.</span><span class="sxs-lookup"><span data-stu-id="c90f3-103">If you use an OUTPUT clause in an INSERT, UPDATE, DELETE, or MERGE command, the count of affected rows is not available.</span></span> <span data-ttu-id="c90f3-104">La aplicación debe contar el número de filas del conjunto de filas que devuelve la cláusula OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="c90f3-104">The application must count the number of rows in the rowset that is returned by the OUTPUT clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c90f3-105">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c90f3-105">See Also</span></span>  
 [<span data-ttu-id="c90f3-106">Crear una aplicación de proveedor OLE DB de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="c90f3-106">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
