---
title: Motor de base de datos de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server]
- SQL Server Database Engine
ms.assetid: 65e2f424-1386-45a6-8912-bd053f434073
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a6c243115e940f7af085c0068d2ca5c277aa5162
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663078"
---
# <a name="sql-server-database-engine"></a><span data-ttu-id="5d57f-102">Motor de base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5d57f-102">SQL Server Database Engine</span></span>
  <span data-ttu-id="5d57f-103">[!INCLUDE[ssDE](../includes/ssde-md.md)] es el servicio principal para almacenar, procesar y proteger los datos.</span><span class="sxs-lookup"><span data-stu-id="5d57f-103">The [!INCLUDE[ssDE](../includes/ssde-md.md)] is the core service for storing, processing, and securing data.</span></span> <span data-ttu-id="5d57f-104">El [!INCLUDE[ssDE](../includes/ssde-md.md)] proporciona acceso controlado y procesamiento de transacciones rápido para cumplir con los requisitos de las aplicaciones consumidoras de datos más exigentes de su empresa.</span><span class="sxs-lookup"><span data-stu-id="5d57f-104">The [!INCLUDE[ssDE](../includes/ssde-md.md)] provides controlled access and rapid transaction processing to meet the requirements of the most demanding data consuming applications within your enterprise.</span></span>

 <span data-ttu-id="5d57f-105">Use [!INCLUDE[ssDE](../includes/ssde-md.md)] para crear bases de datos relacionales para el procesamiento de transacciones en línea o datos de procesamiento analíticos en línea.</span><span class="sxs-lookup"><span data-stu-id="5d57f-105">Use the [!INCLUDE[ssDE](../includes/ssde-md.md)] to create relational databases for online transaction processing or online analytical processing data.</span></span> <span data-ttu-id="5d57f-106">Se pueden crear tablas para almacenar datos y objetos de base de datos como índices, vistas y procedimientos almacenados para ver, administrar y proteger los datos.</span><span class="sxs-lookup"><span data-stu-id="5d57f-106">This includes creating tables for storing data, and database objects such as indexes, views, and stored procedures for viewing, managing, and securing data.</span></span> <span data-ttu-id="5d57f-107">Puede usar [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para administrar los objetos de bases de datos y [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] para capturar eventos de servidor.</span><span class="sxs-lookup"><span data-stu-id="5d57f-107">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to manage the database objects, and [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to capture server events.</span></span>

 <span data-ttu-id="5d57f-108">Icono **buscar contenido por área** ![pequeña carpeta de archivos](../../2014/integration-services/media/filefolder-small.gif "Icono pequeño de carpeta de archivos") novedades [(motor de base de datos)](whats-new-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="5d57f-108">**Browse Content by Area** ![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [What's New (Database Engine)](whats-new-in-sql-server-2016.md)</span></span>

 <span data-ttu-id="5d57f-109">![Icono pequeño de carpeta de archivos](../../2014/integration-services/media/filefolder-small.gif "Icono pequeño de carpeta de archivos") [SQL Server motor de base de datos compatibilidad con versiones anteriores](sql-server-database-engine-backward-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="5d57f-109">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [SQL Server Database Engine Backward Compatibility](sql-server-database-engine-backward-compatibility.md)</span></span>

 <span data-ttu-id="5d57f-110">![Icono pequeño de carpeta de archivos](../../2014/integration-services/media/filefolder-small.gif "Icono pequeño de carpeta de archivos") [herramientas de administración de SQL Server compatibilidad con versiones anteriores](../../2014/database-engine/sql-server-management-tools-backward-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="5d57f-110">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [SQL Server Management Tools Backward Compatibility](../../2014/database-engine/sql-server-management-tools-backward-compatibility.md)</span></span>

 <span data-ttu-id="5d57f-111">![Icono pequeño de carpeta de archivos](../../2014/integration-services/media/filefolder-small.gif "Icono pequeño de carpeta de archivos") [características y tareas de base de datos](../../2014/database-engine/database-engine-features-and-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="5d57f-111">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Database Features and Tasks](../../2014/database-engine/database-engine-features-and-tasks.md)</span></span>

 <span data-ttu-id="5d57f-112">![Icono pequeño de carpeta de archivos](../../2014/integration-services/media/filefolder-small.gif "Icono pequeño de carpeta de archivos") [referencia técnica](../../2014/database-engine/technical-reference-database-engine.md)</span><span class="sxs-lookup"><span data-stu-id="5d57f-112">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Technical Reference](../../2014/database-engine/technical-reference-database-engine.md)</span></span>

 <span data-ttu-id="5d57f-113">![Icono pequeño de carpeta de archivos](../../2014/integration-services/media/filefolder-small.gif "Icono pequeño de carpeta de archivos") [referencia de Transact-SQL](/sql/t-sql/language-reference)</span><span class="sxs-lookup"><span data-stu-id="5d57f-113">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Transact-SQL Reference](/sql/t-sql/language-reference)</span></span>

 <span data-ttu-id="5d57f-114">![Icono pequeño de carpeta de archivos](../../2014/integration-services/media/filefolder-small.gif "Icono pequeño de carpeta de archivos") [referencia de XQuery](/sql/xquery/xquery-language-reference-sql-server)</span><span class="sxs-lookup"><span data-stu-id="5d57f-114">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [XQuery Reference](/sql/xquery/xquery-language-reference-sql-server)</span></span>

## <a name="see-also"></a><span data-ttu-id="5d57f-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5d57f-115">See Also</span></span>
 [<span data-ttu-id="5d57f-116">Centro de recursos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5d57f-116">SQL Server Resource Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=219676)


