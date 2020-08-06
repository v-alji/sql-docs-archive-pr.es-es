---
title: Quitar UDT&#39;s con el nombre de los tipos de datos de fecha y hora reservados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- time data type [SQL Server], UDTs
- date data type [SQL Server], UDTs
ms.assetid: 48f109af-b1d1-4f03-a7e3-8a0b05ed94e8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 827f060b309a7a620fd448554b074f45d78d3cb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675139"
---
# <a name="remove-udt39s-named-after-the-reserved-date-and-time-data-types"></a><span data-ttu-id="a840b-102">Quitar UDT&#39;s con el nombre de los tipos de datos de fecha y hora reservados</span><span class="sxs-lookup"><span data-stu-id="a840b-102">Remove UDT&#39;s named after the reserved DATE and TIME data types</span></span>
  <span data-ttu-id="a840b-103">El Asesor de actualizaciones detectó un tipo definido por el usuario (UDT) que se denomina después de un término reservado para los tipos de datos `date` o `time`.</span><span class="sxs-lookup"><span data-stu-id="a840b-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for either the `date` or the `time` data types.</span></span>  
  
## <a name="component"></a><span data-ttu-id="a840b-104">Componente</span><span class="sxs-lookup"><span data-stu-id="a840b-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="a840b-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="a840b-105">Description</span></span>  
 <span data-ttu-id="a840b-106">Los términos usados para los tipos de datos no se deben utilizar como nombres para el Common Language Runtime (CLR) o alias UDTs.</span><span class="sxs-lookup"><span data-stu-id="a840b-106">The terms used for data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="a840b-107">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="a840b-107">Corrective Action</span></span>  
 <span data-ttu-id="a840b-108">Elimine el UDT que se denomina con el tipo de datos y vuelva a crearlo con un nombre no reservado.</span><span class="sxs-lookup"><span data-stu-id="a840b-108">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
  
