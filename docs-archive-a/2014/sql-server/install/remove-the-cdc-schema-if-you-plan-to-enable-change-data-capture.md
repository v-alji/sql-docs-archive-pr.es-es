---
title: Quitar el esquema CDC si tiene previsto habilitar la captura de datos modificados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- cdc schema
- change data capture
ms.assetid: 6a84aa25-0f31-4be3-b2dd-4f249b8254ae
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: abdb33fa3d1ff022a65ed569f19d48bcf4468501
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675140"
---
# <a name="remove-the-cdc-schema-if-you-plan-to-enable-change-data-capture"></a><span data-ttu-id="d0f74-102">Quitar el esquema cdc si se piensa habilitar la captura de datos modificados</span><span class="sxs-lookup"><span data-stu-id="d0f74-102">Remove the cdc schema if you plan to enable change data capture</span></span>
  <span data-ttu-id="d0f74-103">Una base de datos ya contiene un esquema cdc.</span><span class="sxs-lookup"><span data-stu-id="d0f74-103">A database already contains a cdc schema.</span></span> <span data-ttu-id="d0f74-104">Si piensa habilitar la captura de datos modificados después de la actualización, debe quitar primero este esquema cdc.</span><span class="sxs-lookup"><span data-stu-id="d0f74-104">If you plan to enable change data capture after upgrade, you must first drop this cdc schema.</span></span> <span data-ttu-id="d0f74-105">Al habilitar una base de datos para la captura de datos modificados, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] creará un nuevo esquema cdc.</span><span class="sxs-lookup"><span data-stu-id="d0f74-105">When you enable a database for change data capture, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] will create a new schema named cdc.</span></span>  
  
  
