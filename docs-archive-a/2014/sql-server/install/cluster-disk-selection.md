---
title: Selección de disco de clúster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- cluster disk selection
ms.assetid: 0d6b863d-5972-4a20-9990-64ee8016fea6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0f53d6d3f623254d2b17996be7fd5b8235dca223
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672500"
---
# <a name="cluster-disk-selection"></a><span data-ttu-id="0610e-102">Selección de disco en clúster</span><span class="sxs-lookup"><span data-stu-id="0610e-102">Cluster Disk Selection</span></span>
  <span data-ttu-id="0610e-103">Utilice la página **Selección de disco de clúster** del Asistente para la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para seleccionar el recurso de disco de clúster compartido para el clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0610e-103">Use the **Cluster Disk Selection** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to select the shared cluster disk resource for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span> <span data-ttu-id="0610e-104">El disco de clúster es donde se colocarán los datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0610e-104">The cluster disk is where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data will be placed.</span></span>  
  
 <span data-ttu-id="0610e-105">Un disco de clúster compartido no es un requisito para las [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] instalaciones de clústeres.</span><span class="sxs-lookup"><span data-stu-id="0610e-105">A shared cluster disk is not a requirement for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] cluster installations.</span></span> <span data-ttu-id="0610e-106">Un servidor de archivos SMB es un almacenamiento admitido para las [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] instalaciones de clústeres de conmutación por error y se puede especificar mediante la página **directorios de datos de motor de base de datos** antes de completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="0610e-106">An SMB file server is a supported storage for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] failover cluster installations, and can be specified by using the **Database Engine - Data Directories** page before completing the installation.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="0610e-107">Si ha seleccionado Analysis Services para que se instale, debe especificar un disco de clúster compartido.</span><span class="sxs-lookup"><span data-stu-id="0610e-107">If you have selected Analysis Services to be installed, you must specify a shared cluster disk.</span></span>  
>   
>  <span data-ttu-id="0610e-108">Si tiene previsto habilitar FILESTREAM en esta instancia de clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], debe especificar un disco de clúster compartido.</span><span class="sxs-lookup"><span data-stu-id="0610e-108">If you plan to enable FILESTREAM on this [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance, you must specify a shared cluster disk.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0610e-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="0610e-109">Options</span></span>  
 <span data-ttu-id="0610e-110">**Discos compartidos**</span><span class="sxs-lookup"><span data-stu-id="0610e-110">**Shared Disks**</span></span>  
 <span data-ttu-id="0610e-111">Seleccione un disco único en la lista.</span><span class="sxs-lookup"><span data-stu-id="0610e-111">Select a single disk from the list.</span></span> <span data-ttu-id="0610e-112">El disco de clúster es donde se colocarán los datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0610e-112">The cluster disk is where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data will be placed.</span></span>  
  
 <span data-ttu-id="0610e-113">Solo puede especificarse un disco.</span><span class="sxs-lookup"><span data-stu-id="0610e-113">Only one disk can be specified.</span></span> <span data-ttu-id="0610e-114">Si selecciona el grupo que contiene el recurso de quórum de clúster, se mostrará un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="0610e-114">If you select the group containing the cluster quorum resource, a warning will be displayed.</span></span> <span data-ttu-id="0610e-115">Se recomienda no realizar la instalación en el recurso de quórum de clúster.</span><span class="sxs-lookup"><span data-stu-id="0610e-115">We recommend that you do not install to the cluster quorum resource.</span></span>  
  
 <span data-ttu-id="0610e-116">**Discos compartidos disponibles**</span><span class="sxs-lookup"><span data-stu-id="0610e-116">**Available Shared Disks**</span></span>  
 <span data-ttu-id="0610e-117">Muestra una lista de los discos disponibles, si cada uno está calificado como disco compartido, y una descripción de cada recurso de disco.</span><span class="sxs-lookup"><span data-stu-id="0610e-117">Displays a list of available disks, whether each is qualified as a shared disk, and a description of each disk resource.</span></span>  
  
  
