---
title: 'Configuración de Motor de base de datos: FileStream | Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], about FILESTREAM
ms.assetid: 641a10a1-ae52-4d26-8f1c-a032a4aeff02
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ab12b507246a3e13ac59be213813604d531d9a28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747911"
---
# <a name="database-engine-configuration---filestream"></a><span data-ttu-id="a1cab-102">Configuración del motor de base de datos - Secuencia de archivo</span><span class="sxs-lookup"><span data-stu-id="a1cab-102">Database Engine Configuration - Filestream</span></span>
  <span data-ttu-id="a1cab-103">Utilice esta página para habilitar FILESTREAM para esta instalación de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1cab-103">Use this page to enable FILESTREAM for this installation of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="a1cab-104">FILESTREAM integra [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] con un sistema de archivos NTFS almacenando los `varbinary(max)` datos de objetos binarios grandes (BLOB) como archivos en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="a1cab-104">FILESTREAM integrates the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with an NTFS file system by storing `varbinary(max)` binary large object (BLOB) data as files on the file system.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="a1cab-105">pueden insertar, actualizar, consultar, buscar y realizar copias de seguridad de los datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="a1cab-105">statements can insert, update, query, search, and back up FILESTREAM data.</span></span> <span data-ttu-id="a1cab-106">Las interfaces del sistema de archivos de Win32 proporcionan el acceso de la transmisión por secuencias a los datos.</span><span class="sxs-lookup"><span data-stu-id="a1cab-106">Win32 file system interfaces provide streaming access to the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="a1cab-107">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="a1cab-107">UI element list</span></span>  
 <span data-ttu-id="a1cab-108">**Habilitar FILESTREAM para acceso Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="a1cab-108">**Enable FILESTREAM for Transact-SQL access**</span></span>  
 <span data-ttu-id="a1cab-109">Seleccione esta opción para habilitar FILESTREAM para el acceso a [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1cab-109">Select to enable FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span> <span data-ttu-id="a1cab-110">Este control debe comprobarse para que las otras opciones de control estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="a1cab-110">This control must be checked before the other control options will be available.</span></span>  
  
 <span data-ttu-id="a1cab-111">**Habilitar FILESTREAM para el acceso de transmisión por secuencias de E/S de archivos**</span><span class="sxs-lookup"><span data-stu-id="a1cab-111">**Enable FILESTREAM for file I/O streaming access**</span></span>  
 <span data-ttu-id="a1cab-112">Seleccione esta opción para habilitar el acceso de transmisión por secuencias de Win32 para FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="a1cab-112">Select to enable Win32 streaming access for FILESTREAM.</span></span>  
  
 <span data-ttu-id="a1cab-113">**Nombre de recurso compartido de Windows**</span><span class="sxs-lookup"><span data-stu-id="a1cab-113">**Windows share name**</span></span>  
 <span data-ttu-id="a1cab-114">Utilice este control para escribir el nombre del recurso compartido de Windows en el que los datos de FILESTREAM se almacenarán.</span><span class="sxs-lookup"><span data-stu-id="a1cab-114">Use this control to enter the name of the Windows share in which the FILESTREAM data will be stored.</span></span>  
  
 <span data-ttu-id="a1cab-115">**Permitir que los clientes remotos tengan acceso de transmisión por secuencias a los datos de FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="a1cab-115">**Allow remote clients to have streaming access to FILESTREAM data**</span></span>  
 <span data-ttu-id="a1cab-116">Seleccione este control para permitir que los clientes remotos tengan acceso a estos datos de FILESTREAM en este servidor.</span><span class="sxs-lookup"><span data-stu-id="a1cab-116">Select this control to allow remote clients to access this FILESTREAM data on this server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1cab-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1cab-117">See Also</span></span>  
 <span data-ttu-id="a1cab-118">[Habilitar y configurar FILESTREAM](../../relational-databases/blob/enable-and-configure-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="a1cab-118">[Enable and Configure FILESTREAM](../../relational-databases/blob/enable-and-configure-filestream.md) </span></span>  
 [<span data-ttu-id="a1cab-119">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a1cab-119">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
