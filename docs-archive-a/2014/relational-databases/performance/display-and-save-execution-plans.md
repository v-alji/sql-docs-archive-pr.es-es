---
title: Mostrar y guardar planes de ejecución | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Showplan results
- execution plans [SQL Server]
- queries [SQL Server], tuning
- execution plans [SQL Server], how-to topics
- SQL Server Management Studio [SQL Server], execution plans
- tuning queries [SQL Server]
ms.assetid: bcd6f094-c613-4835-ae19-4caaadb4bb17
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e236ed2a298bc8fc9a829948a864f6f5c27a2ba2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745233"
---
# <a name="display-and-save-execution-plans"></a><span data-ttu-id="c0c05-102">Mostrar y guardar planes de ejecución</span><span class="sxs-lookup"><span data-stu-id="c0c05-102">Display and Save Execution Plans</span></span>
  <span data-ttu-id="c0c05-103">En esta sección se explica cómo visualizar los planes de ejecución y cómo guardarlos en un archivo de formato XML mediante Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0c05-103">This section explains how to display execution plans and how to save execution plans to a file in XML format by using Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c0c05-104">Los planes de ejecución muestran de forma gráfica los métodos de recuperación de datos que utiliza el optimizador de consultas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0c05-104">Execution plans graphically display the data retrieval methods chosen by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query optimizer.</span></span> <span data-ttu-id="c0c05-105">Los planes de ejecución representan el costo de ejecución de las instrucciones y consultas específicas en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en lugar de la representación tabular que crean las instrucciones SET SHOWPLAN_ALL o SET SHOWPLAN_TEXT.</span><span class="sxs-lookup"><span data-stu-id="c0c05-105">Execution plans represent the execution cost of specific statements and queries in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using icons rather than the tabular representation produced by the SET SHOWPLAN_ALL or SET SHOWPLAN_TEXT statements.</span></span> <span data-ttu-id="c0c05-106">Este enfoque gráfico resulta muy útil para comprender las características de rendimiento de una consulta.</span><span class="sxs-lookup"><span data-stu-id="c0c05-106">This graphical approach is very useful for understanding the performance characteristics of a query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0c05-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c0c05-107">In This Section</span></span>  
  
-   [<span data-ttu-id="c0c05-108">Mostrar el plan de ejecución estimado</span><span class="sxs-lookup"><span data-stu-id="c0c05-108">Display the Estimated Execution Plan</span></span>](display-the-estimated-execution-plan.md)  
  
-   [<span data-ttu-id="c0c05-109">Mostrar un plan de ejecución real</span><span class="sxs-lookup"><span data-stu-id="c0c05-109">Display an Actual Execution Plan</span></span>](display-an-actual-execution-plan.md)  
  
-   [<span data-ttu-id="c0c05-110">Guardar un plan de ejecución en formato XML</span><span class="sxs-lookup"><span data-stu-id="c0c05-110">Save an Execution Plan in XML Format</span></span>](save-an-execution-plan-in-xml-format.md)  
  
  
