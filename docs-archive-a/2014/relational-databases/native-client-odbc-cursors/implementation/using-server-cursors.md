---
title: Usar cursores de servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC applications, cursors
- cursors [ODBC], server cursors
- ODBC cursors, server cursors
- server cursors [SQL Server]
ms.assetid: 8a6d99b7-10b8-4474-8639-4914b25ba170
author: rothja
ms.author: jroth
ms.openlocfilehash: e596af3c46849313d813ce2d7f1dab2a7425c090
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671060"
---
# <a name="using-server-cursors"></a><span data-ttu-id="f8516-102">Utilizar cursores de servidor</span><span class="sxs-lookup"><span data-stu-id="f8516-102">Using Server Cursors</span></span>
  <span data-ttu-id="f8516-103">Si una aplicación ODBC establece cualquiera de los atributos de cursor de ODBC en algo distinto de los valores predeterminados, el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client solicita al servidor que implemente un cursor de servidor de API del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="f8516-103">If an ODBC application sets any of the ODBC cursor attributes to anything other than the defaults, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver requests the server to implement an API server cursor of the same type.</span></span> <span data-ttu-id="f8516-104">El uso de cursores de servidor de API libera memoria en el cliente y reduce significativamente el tráfico de red entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f8516-104">Using API server cursors frees memory on the client and can significantly reduce network traffic between the client and server.</span></span>  
  
 <span data-ttu-id="f8516-105">El hecho de que los cursores de servidor de API no admitan actualmente todas las instrucciones SQL puede representar un inconveniente.</span><span class="sxs-lookup"><span data-stu-id="f8516-105">A potential drawback of API server cursors is that they currently do not support all SQL statements.</span></span> <span data-ttu-id="f8516-106">Los cursores de servidor de API no se pueden utilizar para ejecutar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f8516-106">API server cursors cannot be used to execute:</span></span>  
  
-   <span data-ttu-id="f8516-107">Lotes o procedimientos almacenados que devuelven varios conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="f8516-107">Batches or stored procedures that return multiple result sets.</span></span>  
  
-   <span data-ttu-id="f8516-108">Instrucciones SELECT que contienen cláusulas COMPUTE, COMPUTE BY, FOR BROWSE o INTO.</span><span class="sxs-lookup"><span data-stu-id="f8516-108">SELECT statements that contain COMPUTE, COMPUTE BY, FOR BROWSE, or INTO clauses.</span></span>  
  
-   <span data-ttu-id="f8516-109">Una instrucción EXECUTE que haga referencia a un procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="f8516-109">An EXECUTE statement referencing a remote stored procedure.</span></span>  
  
 <span data-ttu-id="f8516-110">Si se está conectado a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], ejecutar una instrucción con estas características utilizando un cursor de servidor hace que el cursor se convierta en un conjunto de resultados predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f8516-110">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], executing a statement with these characteristics using a server cursor causes the cursor being converted to a default result set.</span></span> <span data-ttu-id="f8516-111">Si está conectado a versiones anteriores de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], produce un error.</span><span class="sxs-lookup"><span data-stu-id="f8516-111">When connected to earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it causes an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8516-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f8516-112">See Also</span></span>  
 [<span data-ttu-id="f8516-113">Cómo se implementan los cursores</span><span class="sxs-lookup"><span data-stu-id="f8516-113">How Cursors Are Implemented</span></span>](how-cursors-are-implemented.md)  
  
  
