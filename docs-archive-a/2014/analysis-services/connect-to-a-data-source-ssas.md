---
title: Conectarse a un origen de datos (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conndatasource.f1
ms.assetid: 1e2b17e9-092b-4af1-8a58-c52b8fe10ff1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4fe7f7d5b31118369b8ce2a855b955e44f661dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670023"
---
# <a name="connect-to-a-data-source-ssas"></a><span data-ttu-id="2df6e-102">Conectarse a un origen de datos (SSAS)</span><span class="sxs-lookup"><span data-stu-id="2df6e-102">Connect to a Data Source (SSAS)</span></span>
  <span data-ttu-id="2df6e-103">Esta página del **Asistente para la importación de tablas** le permite crear una nueva conexión con un origen de datos con diversidad de orígenes de datos, como bases de datos relacionales, fuentes de distribución de datos y archivos.</span><span class="sxs-lookup"><span data-stu-id="2df6e-103">This page of the **Table Import Wizard** enables you to create a new data source connection to a variety of data sources, such as relational databases, data feeds, and files.</span></span> <span data-ttu-id="2df6e-104">Para tener acceso al asistente desde [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el menú **Modelo** , haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="2df6e-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="2df6e-105">Para conectarse a un origen de datos, debe tener instalado en el equipo el proveedor adecuado.</span><span class="sxs-lookup"><span data-stu-id="2df6e-105">To connect to a data source, you must have the appropriate provider installed on your machine.</span></span> <span data-ttu-id="2df6e-106">También debe tener el proveedor adecuado instalado en el servidor de bases de datos del área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2df6e-106">You must also have the appropriate provider installed on the workspace database server.</span></span> <span data-ttu-id="2df6e-107">Para los servidores de 32 bits (x86), se deben instalar los proveedores de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="2df6e-107">For 32-bit (x86) servers, 32-bit providers must be installed.</span></span> <span data-ttu-id="2df6e-108">Para los servidores de 64 bits (x64), se deben instalar los proveedores de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="2df6e-108">For 64-bit (x64) servers, 64-bit providers must be installed.</span></span>  
  
 [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] <span data-ttu-id="2df6e-109">siempre se ejecuta en un proceso de 32 bits, independientemente de la arquitectura.</span><span class="sxs-lookup"><span data-stu-id="2df6e-109">always runs in a 32-bit process, regardless of architecture.</span></span> <span data-ttu-id="2df6e-110">Cuando ejecute [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] en un equipo de 64 bits, debe tener en cuenta lo siguiente al instalar los proveedores de datos:</span><span class="sxs-lookup"><span data-stu-id="2df6e-110">When running [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] on a 64-bit machine, you should be aware of the following when installing data providers:</span></span>  
  
-   <span data-ttu-id="2df6e-111">Para los proveedores que admiten la instalación en paralelo de proveedores de 32 y 64 bits, debe instalar los dos proveedores.</span><span class="sxs-lookup"><span data-stu-id="2df6e-111">For providers that support side-by-side installation of 32-bit and 64-bit providers, you should install both providers.</span></span>  
  
-   <span data-ttu-id="2df6e-112">Para el proveedor ACE, debe instalar la versión de 64 bits del proveedor.</span><span class="sxs-lookup"><span data-stu-id="2df6e-112">For the ACE provider, you must install the 64-bit version of the provider.</span></span> <span data-ttu-id="2df6e-113">Dado que Office instala automáticamente el proveedor ACE, no debe ejecutar una versión de 32 bits de Microsoft Office en un equipo de 64 bits que hospeda el servidor de bases de datos del área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2df6e-113">Because Office automatically installs the ACE provider, you should not run a 32-bit version of Microsoft Office on a 64-bit machine hosting the workspace database server.</span></span>  
  
     <span data-ttu-id="2df6e-114">El proveedor ACE se utiliza para importar datos de archivos de texto, de Excel y de Access.</span><span class="sxs-lookup"><span data-stu-id="2df6e-114">The ACE provider is used to import from Text, Excel, and Access files.</span></span> <span data-ttu-id="2df6e-115">Si no necesita estos orígenes de datos, puede ejecutar una versión de 32 bits de Microsoft Office en un equipo que ejecuta un servidor de bases de datos del área de trabajo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="2df6e-115">If support for these data sources is not needed, you can then run a 32-bit version of Microsoft Office on a machine running a 64-bit workspace database server.</span></span>  
  
-   <span data-ttu-id="2df6e-116">Para otros proveedores que no admiten la instalación en paralelo de proveedores de 32 y 64 bits, debe instalar el proveedor de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="2df6e-116">For other providers that do not support side-by-side installation of 32-bit and 64-bit providers, you must install the 32-bit provider.</span></span> <span data-ttu-id="2df6e-117">Si solo dispone de equipos de 64 bits, debe usar un equipo remoto con un proveedor de 64 bits instalado como servidor de bases de datos del área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2df6e-117">If only 64-bit machines are available, you must use a remote machine with a 64-bit provider installed as the workspace database server.</span></span>  
  
  
