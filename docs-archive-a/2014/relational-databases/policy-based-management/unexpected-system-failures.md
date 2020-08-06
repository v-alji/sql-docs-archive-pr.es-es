---
title: Errores del sistema inesperados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 1679bf9e-a2ef-4f90-8907-a002f7341a7d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b791ba0e3f709288a4e2c5b6add4e74e15d56dee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670983"
---
# <a name="unexpected-system-failures"></a><span data-ttu-id="e8c49-102">Errores del sistema inesperados</span><span class="sxs-lookup"><span data-stu-id="e8c49-102">Unexpected System Failures</span></span>
  <span data-ttu-id="e8c49-103">Esta regla comprueba si el evento SYSTEM 6008 aparece en el registro de eventos del equipo.</span><span class="sxs-lookup"><span data-stu-id="e8c49-103">This rule checks for SYSTEM Event 6008 in the computer event log.</span></span> <span data-ttu-id="e8c49-104">Este evento indica un cierre del sistema inesperado.</span><span class="sxs-lookup"><span data-stu-id="e8c49-104">This event indicates an unexpected system shutdown.</span></span> <span data-ttu-id="e8c49-105">El sistema podría ser inestable y no proporcionar la estabilidad e integridad que se exigen para hospedar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8c49-105">The system might be unstable and might not provide the stability and integrity that is required to host an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="e8c49-106">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="e8c49-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="e8c49-107">Trate inmediatamente la causa del reinicio inesperado del servidor o mueva la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a otro equipo.</span><span class="sxs-lookup"><span data-stu-id="e8c49-107">Immediately address the cause of the unexpected server restarts, or move the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to another computer.</span></span>  
  
  
