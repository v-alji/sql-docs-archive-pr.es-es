---
title: Actualizar las expresiones de XPath de OPENXML para quitar las funciones no admitidas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- OPENXML queries
ms.assetid: b459abaf-8787-4b65-9231-ae30e5469fd0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2c64408d6d705654014b6d071012001374a5f486
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672423"
---
# <a name="update-openxml-xpath-expressions-to-remove-unsupported-functions"></a><span data-ttu-id="c5835-102">Actualizar expresiones XPath OPENXML para quitar funciones no compatibles</span><span class="sxs-lookup"><span data-stu-id="c5835-102">Update OPENXML XPath expressions to remove unsupported functions</span></span>
  <span data-ttu-id="c5835-103">El Asesor de actualizaciones ha detectado que se está utilizando la funcionalidad de XPath.</span><span class="sxs-lookup"><span data-stu-id="c5835-103">Upgrade Advisor detected the use of XPath functionality.</span></span> <span data-ttu-id="c5835-104">Es posible que tenga problemas con los cambios realizados en la funcionalidad de XPath para las características de OPENXML tras la actualización.</span><span class="sxs-lookup"><span data-stu-id="c5835-104">You may be affected by changes in XPath functionality for OPENXML features after you upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="c5835-105">Componente</span><span class="sxs-lookup"><span data-stu-id="c5835-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="c5835-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5835-106">Description</span></span>  
 <span data-ttu-id="c5835-107">Ahora, MSXML 3.0 es el motor subyacente que se utiliza para procesar expresiones XPath usadas en consultas OPENXML.</span><span class="sxs-lookup"><span data-stu-id="c5835-107">MSXML 3.0 is now the underlying engine that is used to process XPath expressions that are used within OPENXML queries.</span></span> <span data-ttu-id="c5835-108">MSXML 3.0 tiene un motor XPath 1.0 más estricto en el que se ha quitado la compatibilidad con las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="c5835-108">MSXML 3.0 has a stricter XPath 1.0 engine in which support for the following functions has been removed:</span></span>  
  
-   <span data-ttu-id="c5835-109">format-number()</span><span class="sxs-lookup"><span data-stu-id="c5835-109">format-number()</span></span>  
  
-   <span data-ttu-id="c5835-110">formatNumber()</span><span class="sxs-lookup"><span data-stu-id="c5835-110">formatNumber()</span></span>  
  
-   <span data-ttu-id="c5835-111">current()</span><span class="sxs-lookup"><span data-stu-id="c5835-111">current()</span></span>  
  
-   <span data-ttu-id="c5835-112">element-available()</span><span class="sxs-lookup"><span data-stu-id="c5835-112">element-available()</span></span>  
  
-   <span data-ttu-id="c5835-113">function-available()</span><span class="sxs-lookup"><span data-stu-id="c5835-113">function-available()</span></span>  
  
-   <span data-ttu-id="c5835-114">system-property()</span><span class="sxs-lookup"><span data-stu-id="c5835-114">system-property()</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c5835-115">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="c5835-115">Corrective Action</span></span>  
 <span data-ttu-id="c5835-116">En el caso de format-number() y formatNumber(), puede utilizar [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5835-116">In the case of format-number() and formatNumber(), you can use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c5835-117">Para las demás funciones no compatibles que aparecen más arriba, no existen soluciones directas.</span><span class="sxs-lookup"><span data-stu-id="c5835-117">For the other unsupported functions listed earlier, there is no direct workaround.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5835-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5835-118">See Also</span></span>  
 <span data-ttu-id="c5835-119">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="c5835-119">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="c5835-120">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="c5835-120">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
