---
title: Mensajes de error | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], types
- ODBC error handling, message types
- errors [ODBC], types
ms.assetid: 46c0c22e-d105-4d5b-bb9d-5694472e8651
author: rothja
ms.author: jroth
ms.openlocfilehash: d004ba320b50896b6f57c5de335d7f7b3d33e87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748770"
---
# <a name="error-messages"></a><span data-ttu-id="27ba4-102">mensajes de error</span><span class="sxs-lookup"><span data-stu-id="27ba4-102">Error Messages</span></span>
  <span data-ttu-id="27ba4-103">El texto de los mensajes devueltos por el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client se coloca en el parámetro *MessageText* de **SQLGetDiagRec**.</span><span class="sxs-lookup"><span data-stu-id="27ba4-103">The text of messages returned by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is placed in the *MessageText* parameter of **SQLGetDiagRec**.</span></span> <span data-ttu-id="27ba4-104">El encabezado del mensaje indica el origen de un error:</span><span class="sxs-lookup"><span data-stu-id="27ba4-104">The source of an error is indicated by the header of the message:</span></span>  
  
 <span data-ttu-id="27ba4-105">[Microsoft][ODBC Driver Manager]</span><span class="sxs-lookup"><span data-stu-id="27ba4-105">[Microsoft][ODBC Driver Manager]</span></span>  
 <span data-ttu-id="27ba4-106">El Administrador de controladores ODBC produce estos errores.</span><span class="sxs-lookup"><span data-stu-id="27ba4-106">These errors are raised by the ODBC Driver Manager.</span></span>  
  
 <span data-ttu-id="27ba4-107">[Microsoft][ODBC Cursor Library]</span><span class="sxs-lookup"><span data-stu-id="27ba4-107">[Microsoft][ODBC Cursor Library]</span></span>  
 <span data-ttu-id="27ba4-108">La biblioteca de cursores ODBC produce estos errores.</span><span class="sxs-lookup"><span data-stu-id="27ba4-108">These errors are raised by the ODBC cursor library.</span></span>  
  
 <span data-ttu-id="27ba4-109">[Microsoft][SQL Server Native Client]</span><span class="sxs-lookup"><span data-stu-id="27ba4-109">[Microsoft][SQL Server Native Client]</span></span>  
 <span data-ttu-id="27ba4-110">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client genera estos errores.</span><span class="sxs-lookup"><span data-stu-id="27ba4-110">These errors are raised by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="27ba4-111">Si no hay ningún otro nodo con el nombre de una biblioteca de red o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el error se produjo en el controlador.</span><span class="sxs-lookup"><span data-stu-id="27ba4-111">If there are no other nodes with either the name of a Net-Library or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], then the error was encountered in the driver.</span></span>  
  
 <span data-ttu-id="27ba4-112">Microsoft [SQL Server Native Client] [*Net-nombredetransportedered*]</span><span class="sxs-lookup"><span data-stu-id="27ba4-112">[Microsoft][SQL Server Native Client][*Net-Transportname*]</span></span>  
 <span data-ttu-id="27ba4-113">Estos errores se producen en la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] biblioteca de red, donde *net-nombredetransportedered* es el nombre para mostrar de un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transporte de red de cliente (por ejemplo, canalizaciones con nombre, memoria compartida, Sockets TCP/IP o Via).</span><span class="sxs-lookup"><span data-stu-id="27ba4-113">These errors are raised by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Net-Library, where *Net-Transportname* is the display name of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network transport (for example, Named Pipes, Shared Memory, TCP/IP Sockets, or VIA).</span></span> <span data-ttu-id="27ba4-114">El resto del mensaje de error contiene la función de biblioteca de red a la que se ha llamado y la función a la que se ha llamado en la API de red subyacente mediante la función TDS.</span><span class="sxs-lookup"><span data-stu-id="27ba4-114">The remainder of the error message contains the Net-Library function called and the function called in the underlying network API by the TDS function.</span></span> <span data-ttu-id="27ba4-115">El código de error *pfNative* devuelto con estos errores es el código de error de la pila del Protocolo de red subyacente.</span><span class="sxs-lookup"><span data-stu-id="27ba4-115">The *pfNative* error code returned with these errors is the error code from the underlying network protocol stack.</span></span>  
  
 <span data-ttu-id="27ba4-116">[Microsoft][SQL Server Native Client][[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]]</span><span class="sxs-lookup"><span data-stu-id="27ba4-116">[Microsoft][SQL Server Native Client][[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]]</span></span>  
 <span data-ttu-id="27ba4-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] produce estos errores.</span><span class="sxs-lookup"><span data-stu-id="27ba4-117">These errors are raised by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="27ba4-118">El resto del mensaje de error es el texto del mensaje de error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27ba4-118">The remainder of the error message is the text of the error message from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="27ba4-119">El código *pfNative* devuelto con estos errores es el número de error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27ba4-119">The *pfNative* code returned with these errors is the error number from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="27ba4-120">Para obtener más información acerca de una lista de mensajes de error (y sus números) que puede devolver [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vea la descripción y las columnas de error de la tabla del sistema **sysmessages** en la base de datos **maestra** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27ba4-120">For more information about a list of error messages (and their numbers) that can be returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the description and error columns of the **sysmessages** system table in the **master** database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ba4-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27ba4-121">See Also</span></span>  
 [<span data-ttu-id="27ba4-122">Controlar errores y mensajes</span><span class="sxs-lookup"><span data-stu-id="27ba4-122">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
