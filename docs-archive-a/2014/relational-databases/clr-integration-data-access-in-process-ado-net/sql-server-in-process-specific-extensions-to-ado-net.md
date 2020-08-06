---
title: SQL Server extensiones específicas en proceso a ADO.NET | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- data access [CLR integration]
- ADO.NET [CLR integration]
- common language runtime [SQL Server], ADO.NET
- database objects [CLR integration], in-process extensions
- in-process data access providers [CLR integration]
- extensions [CLR integration]
ms.assetid: 781b812e-eb14-472a-85fa-aa4cdb929bee
author: rothja
ms.author: jroth
ms.openlocfilehash: 37d8aedc1d8f93739c2e9386665adfc67b43e312
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677164"
---
# <a name="sql-server-in-process-specific-extensions-to-adonet"></a><span data-ttu-id="a7010-102">Extensiones específicas en proceso de SQL Server a ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a7010-102">SQL Server In-Process Specific Extensions to ADO.NET</span></span>
  <span data-ttu-id="a7010-103">Hay cuatro extensiones funcionales principales a ADO.NET que son específicamente para el uso en proceso.</span><span class="sxs-lookup"><span data-stu-id="a7010-103">There are four main functional extensions to ADO.NET that are specifically for in-process use.</span></span> <span data-ttu-id="a7010-104">En los siguientes temas se tratan estas extensiones en detalle.</span><span class="sxs-lookup"><span data-stu-id="a7010-104">The following topics will cover these extensions in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a7010-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a7010-105">In This Section</span></span>  
 [<span data-ttu-id="a7010-106">Objeto SqlContext</span><span class="sxs-lookup"><span data-stu-id="a7010-106">SqlContext Object</span></span>](sqlcontext-object.md)  
 <span data-ttu-id="a7010-107">Esta clase proporciona acceso a las demás extensiones abstrayendo el contexto de llamador de una rutina de SQL Server que ejecuta el código administrado en proceso.</span><span class="sxs-lookup"><span data-stu-id="a7010-107">This class provides access to the other extensions by abstracting the context of a caller of a SQL Server routine that executes managed code in-process.</span></span>  
  
 [<span data-ttu-id="a7010-108">SqlPipe, objetos</span><span class="sxs-lookup"><span data-stu-id="a7010-108">SqlPipe Object</span></span>](sqlpipe-object.md)  
 <span data-ttu-id="a7010-109">Esta clase contiene rutinas para enviar resultados tabulares y mensajes al cliente.</span><span class="sxs-lookup"><span data-stu-id="a7010-109">This class contains routines to send tabular results and messages to the client.</span></span>  
  
 [<span data-ttu-id="a7010-110">Objeto SqlTriggerContext</span><span class="sxs-lookup"><span data-stu-id="a7010-110">SqlTriggerContext Object</span></span>](sqltriggercontext-object.md)  
 <span data-ttu-id="a7010-111">Esta clase proporciona información sobre el contexto en el que se ejecuta un desencadenador.</span><span class="sxs-lookup"><span data-stu-id="a7010-111">This class provides information on the context in which a trigger is run.</span></span>  
  
 [<span data-ttu-id="a7010-112">SqlDataRecord, objeto</span><span class="sxs-lookup"><span data-stu-id="a7010-112">SqlDataRecord Object</span></span>](sqldatarecord-object.md)  
 <span data-ttu-id="a7010-113">La clase SqlDataRecord representa una única fila de datos, junto con sus metadatos relacionados, y permite que los procedimientos almacenados devuelvan al cliente conjuntos de resultados personalizados.</span><span class="sxs-lookup"><span data-stu-id="a7010-113">The SqlDataRecord class represents a single row of data, along with its related metadata, and allows stored procedures to return custom result sets to the client.</span></span>  
  
  
