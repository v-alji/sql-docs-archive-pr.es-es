---
title: Tipos definidos por el usuario de CLR grandes (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- large CLR user-defined types
ms.assetid: b65eb61d-ccf6-49c0-98e7-9a4ef4b2f790
author: rothja
ms.author: jroth
ms.openlocfilehash: 27f0c13caea8c4aca63d78238509c6d05f1bf7bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745255"
---
# <a name="large-clr-user-defined-types"></a><span data-ttu-id="343ee-102">Tipos definidos por el usuario de CLR grandes</span><span class="sxs-lookup"><span data-stu-id="343ee-102">Large CLR User-Defined Types</span></span>
  <span data-ttu-id="343ee-103">En SQL Server 2005, los tipos definidos por el usuario (UDT) en Common Language Runtime (CLR) estaban restringidos a un tamaño de 8.000 bytes.</span><span class="sxs-lookup"><span data-stu-id="343ee-103">In SQL Server 2005, user-defined types (UDTs) in the common language runtime (CLR) were restricted to 8,000 bytes in size.</span></span> <span data-ttu-id="343ee-104">Esta restricción se soluciona en [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="343ee-104">This restriction has been lifted in [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] and later versions.</span></span> <span data-ttu-id="343ee-105">Los UDT CLR se tratan ahora de una manera similar a los tipos de objeto grandes (LOB).</span><span class="sxs-lookup"><span data-stu-id="343ee-105">CLR UDTs are now treated in a similar way to large object (LOB) types.</span></span> <span data-ttu-id="343ee-106">Es decir, los UDT con un tamaño menor o igual que 8.000 bytes se comportan de la misma manera que en SQL Server 2005, pero se admiten UDT de mayor tamaño y notifican su tamaño como "ilimitado".</span><span class="sxs-lookup"><span data-stu-id="343ee-106">That is, UDTs less than or equal to 8,000 bytes behave the same way as in SQL Server 2005, but larger UDTs are supported and report their size as "unlimited".</span></span>  
  
 <span data-ttu-id="343ee-107">Para obtener más información, vea [tipos CLR grandes definidos por el usuario &#40;OLE DB&#41;](../ole-db/large-clr-user-defined-types-ole-db.md) y [tipos CLR grandes definidos por el usuario &#40;&#41;ODBC ](../odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="343ee-107">For more information, see [Large CLR User-Defined Types &#40;OLE DB&#41;](../ole-db/large-clr-user-defined-types-ole-db.md) and [Large CLR User-Defined Types &#40;ODBC&#41;](../odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="use-cases"></a><span data-ttu-id="343ee-108">Casos de uso</span><span class="sxs-lookup"><span data-stu-id="343ee-108">Use Cases</span></span>  
 <span data-ttu-id="343ee-109">Para ODBC, la compatibilidad con UDT grandes incluye la capacidad de enviar los valores de UDT en partes como parámetros de datos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="343ee-109">For ODBC, support for large UDTs includes the ability to send UDT values in pieces as data-at-execution parameters.</span></span> <span data-ttu-id="343ee-110">Esto se hace mediante SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="343ee-110">This is done by using SQLPutData.</span></span>  
  
 <span data-ttu-id="343ee-111">Para OLE DB, la compatibilidad con UDT grandes incluye la capacidad de transmitir en secuencias los valores del UDT a y desde el servidor mediante el enlace ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="343ee-111">For OLE DB, support for large UDTs includes the ability to stream UDT values to and from the server by using ISequentialStream binding.</span></span>  
  
 <span data-ttu-id="343ee-112">Los UDT con un tamaño menor o igual que 8.000 se comportarán como lo hacían en SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="343ee-112">UDTs less than or equal to 8,000 bytes will behave as they did in SQL Server 2005.</span></span> <span data-ttu-id="343ee-113">Para OLE DB, puede transmitir en secuencias todavía los UDT pequeños usando el enlace ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="343ee-113">For OLE DB, you can still stream small UDTs by using ISequentialStream binding.</span></span>  
  
 <span data-ttu-id="343ee-114">A veces el código nativo tendrá que entender el contenido de los UDT CLR, pero no tendrá que crear instancias de los objetos administrados.</span><span class="sxs-lookup"><span data-stu-id="343ee-114">Sometimes native code will have to understand the contents of CLR UDTs, but will not have to instantiate managed objects.</span></span> <span data-ttu-id="343ee-115">Si éste es el caso, puede utilizar la serialización personalizada para convertir los valores de UDT en el servidor en un formato bien conocido para los clientes.</span><span class="sxs-lookup"><span data-stu-id="343ee-115">If this is the case, you can use custom serialization to convert UDT values on the server into a well known format for clients.</span></span>  
  
 <span data-ttu-id="343ee-116">Para las aplicaciones que tienen código de acceso a datos existente, puede aprovechar el comportamiento de los UDT CLR en el cliente recuperando los UDT a través de API nativas y creando instancias de ellos utilizando la interoperabilidad de C++ CLI en aplicaciones de modo mixto.</span><span class="sxs-lookup"><span data-stu-id="343ee-116">For applications that have existing data access code, you can exploit CLR UDT behavior on the client by retrieving UDTs through native APIs and instantiating them by using C++ CLI interop in mixed mode applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="343ee-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="343ee-117">See Also</span></span>  
 [<span data-ttu-id="343ee-118">Características de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="343ee-118">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
