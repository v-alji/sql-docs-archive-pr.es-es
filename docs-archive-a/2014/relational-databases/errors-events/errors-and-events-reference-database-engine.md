---
title: Referencia de errores y eventos de (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server Database Engine]
- Database Engine [SQL Server], errors
- events [SQL Server Database Engine]
ms.assetid: ea928535-6fd1-4738-a8ed-ffb602f3825e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e991accfd0e6fdd4fa25746499308455eff85ce3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747604"
---
# <a name="errors-and-events-reference-database-engine"></a><span data-ttu-id="9c319-102">Referencia de errores y eventos del motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="9c319-102">Errors and Events Reference (Database Engine)</span></span>

<span data-ttu-id="9c319-103">Esta sección contiene los mensajes de error seleccionados Motor de base de datos que requieren una explicación más detallada.</span><span class="sxs-lookup"><span data-stu-id="9c319-103">This section contains selected Database Engine error messages that need further explanation.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="9c319-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9c319-104">In This Section</span></span>  
 <span data-ttu-id="9c319-105">[Eventos y errores de motor de base de datos](database-engine-events-and-errors.md) Describe el formato de [!INCLUDE[ssDE](../../includes/ssde-md.md)] los mensajes de error y explica cómo ver los mensajes de error y devolver mensajes de error a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9c319-105">[Database Engine Events and Errors](database-engine-events-and-errors.md) Describes the format of [!INCLUDE[ssDE](../../includes/ssde-md.md)] error messages and explains how to view error messages and return error messages to applications.</span></span>  
  
 <span data-ttu-id="9c319-106">Proporciona una explicación de los mensajes de error de [!INCLUDE[ssDE](../../includes/ssde-md.md)] , las posibles causas y las medidas que se pueden tomar para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="9c319-106">Provides an explanation of [!INCLUDE[ssDE](../../includes/ssde-md.md)] error messages, possible causes, and any actions you can take to correct the problem.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="9c319-107">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="9c319-107">External Resources</span></span>  
 <span data-ttu-id="9c319-108">Si no encuentra la información que está buscando en la documentación del producto ni en Internet, puede formular una pregunta en la comunidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o solicitar ayuda al servicio de soporte técnico de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9c319-108">If you have not found the information you are looking for in the product documentation or on the Web, you can either ask a question in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] community or request help from [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="9c319-109">En la tabla siguiente se proporcionan vínculos y descripciones de estos recursos.</span><span class="sxs-lookup"><span data-stu-id="9c319-109">The following table links to and describes these resources.</span></span>  
  
|<span data-ttu-id="9c319-110">Recurso</span><span class="sxs-lookup"><span data-stu-id="9c319-110">Resource</span></span>|<span data-ttu-id="9c319-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c319-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="9c319-112">Comunidad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="9c319-112">SQL Server Community</span></span>](https://go.microsoft.com/fwlink/?LinkId=42455)|<span data-ttu-id="9c319-113">Este sitio contiene vínculos a grupos de noticias y foros supervisados por la comunidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9c319-113">This site has links to newsgroups and forums monitored by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] community.</span></span> <span data-ttu-id="9c319-114">También muestra orígenes de información de las comunidades, como blogs y sitios web.</span><span class="sxs-lookup"><span data-stu-id="9c319-114">It also lists community information sources, such as blogs and Web sites.</span></span> <span data-ttu-id="9c319-115">La comunidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es de gran utilidad para obtener respuesta a algunas preguntas, aunque la respuesta no se puede garantizar.</span><span class="sxs-lookup"><span data-stu-id="9c319-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] community is very helpful in answering questions, although an answer cannot be guaranteed.</span></span>|  
|[<span data-ttu-id="9c319-116">Comunidad del Centro para programadores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="9c319-116">SQL Server Developer Center Community</span></span>](https://go.microsoft.com/fwlink/?LinkId=42456)|<span data-ttu-id="9c319-117">El sitio se centra en los grupos de noticias, foros y otros recursos de la comunidad útiles para los programadores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9c319-117">This site focuses on the newsgroups, forums, and other community resources that are useful to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] developers.</span></span>|  
|[<span data-ttu-id="9c319-118">Ayuda y soporte técnico de Microsoft</span><span class="sxs-lookup"><span data-stu-id="9c319-118">Microsoft Help and Support</span></span>](https://go.microsoft.com/fwlink/?linkid=16419)|<span data-ttu-id="9c319-119">Puede utilizar este sitio web para abrir un caso con un profesional de soporte de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9c319-119">You can use this Web site to open a case with a [!INCLUDE[msCoName](../../includes/msconame-md.md)] support professional.</span></span>|  
  
  
