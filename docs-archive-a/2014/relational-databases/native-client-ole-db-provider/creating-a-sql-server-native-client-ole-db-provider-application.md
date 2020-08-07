---
title: Creación de una aplicación de proveedor de OLE DB de SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, application creation
- applications [SQL Server Native Client]
- OLE DB, creating applications
ms.assetid: f3ae6815-f32d-4913-a1a2-2ba2f20cfd88
author: rothja
ms.author: jroth
ms.openlocfilehash: a661f23cdacc4b581dadbe7625cb6e2ea318857f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745269"
---
# <a name="creating-a-sql-server-native-client-ole-db-provider-application"></a><span data-ttu-id="30c6c-102">Crear una aplicación de proveedor OLE DB de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="30c6c-102">Creating a SQL Server Native Client OLE DB Provider Application</span></span>
  <span data-ttu-id="30c6c-103">La creación de una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aplicación de proveedor de OLE DB de Native Client implica estos pasos:</span><span class="sxs-lookup"><span data-stu-id="30c6c-103">Creating a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider application involves these steps:</span></span>  
  
1.  <span data-ttu-id="30c6c-104">Establecer una conexión con un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="30c6c-104">Establishing a connection to a data source.</span></span>  
  
2.  <span data-ttu-id="30c6c-105">Ejecutar un comando.</span><span class="sxs-lookup"><span data-stu-id="30c6c-105">Executing a command.</span></span>  
  
3.  <span data-ttu-id="30c6c-106">Procesar los resultados.</span><span class="sxs-lookup"><span data-stu-id="30c6c-106">Processing the results.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30c6c-107">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="30c6c-107">When possible, use Windows Authentication.</span></span> <span data-ttu-id="30c6c-108">Si la autenticación de Windows no está disponible, solicite a los usuarios que escriban sus credenciales en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="30c6c-108">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="30c6c-109">No guarde las credenciales en un archivo.</span><span class="sxs-lookup"><span data-stu-id="30c6c-109">Avoid storing credentials in a file.</span></span> <span data-ttu-id="30c6c-110">Si tiene que conservar las credenciales, debería cifrarlas con la [cryptoAPI de Win32](https://go.microsoft.com/fwlink/?LinkId=9504).</span><span class="sxs-lookup"><span data-stu-id="30c6c-110">If you must persist credentials, you should encrypt them with [the Win32 cryptoAPI](https://go.microsoft.com/fwlink/?LinkId=9504).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30c6c-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="30c6c-111">In This Section</span></span>  
  
-   [<span data-ttu-id="30c6c-112">Establecer una conexión con un origen de datos</span><span class="sxs-lookup"><span data-stu-id="30c6c-112">Establishing a Connection to a Data Source</span></span>](establishing-a-connection-to-a-data-source.md)  
  
-   [<span data-ttu-id="30c6c-113">Ejecutar un comando</span><span class="sxs-lookup"><span data-stu-id="30c6c-113">Executing a Command</span></span>](executing-a-command.md)  
  
-   [<span data-ttu-id="30c6c-114">Procesar los resultados (ODBC)</span><span class="sxs-lookup"><span data-stu-id="30c6c-114">Processing Results</span></span>](processing-results.md)  
  
-   [<span data-ttu-id="30c6c-115">Acerca de las propiedades de OLE DB</span><span class="sxs-lookup"><span data-stu-id="30c6c-115">About OLE DB Properties</span></span>](about-ole-db-properties.md)  
  
-   [<span data-ttu-id="30c6c-116">Usar la cláusula OUTPUT con OLE DB en SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="30c6c-116">Using the OUTPUT Clause with OLE DB in SQL Server Native Client</span></span>](using-the-output-clause-with-ole-db-in-sql-server-native-client.md)  
  
## <a name="see-also"></a><span data-ttu-id="30c6c-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="30c6c-117">See Also</span></span>  
 [<span data-ttu-id="30c6c-118">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="30c6c-118">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
