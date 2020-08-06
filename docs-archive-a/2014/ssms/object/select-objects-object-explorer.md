---
title: Seleccionar objetos (Explorador de objetos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.selectobjects.f1
ms.assetid: 692477fe-dd7c-403d-acd2-bb108b6077f1
author: stevestein
ms.author: sstein
ms.openlocfilehash: ceec604d9fe07b339af11ed69226d41a7f616678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743887"
---
# <a name="select-objects-object-explorer"></a><span data-ttu-id="fca30-102">Seleccionar objetos (Explorador de objetos)</span><span class="sxs-lookup"><span data-stu-id="fca30-102">Select Objects (Object Explorer)</span></span>
  <span data-ttu-id="fca30-103">Use el cuadro de diálogo **Seleccionar objetos** para agregar un objeto a una lista de otro cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fca30-103">Use the **Select Objects** dialog box to add an object to a list in another dialog box.</span></span> <span data-ttu-id="fca30-104">El título del cuadro de diálogo y las opciones disponibles dependerán de como haya se haya abierto.</span><span class="sxs-lookup"><span data-stu-id="fca30-104">The dialog box title and the options available in the dialog box depend upon how it was opened.</span></span> <span data-ttu-id="fca30-105">Solo aparecerán las opciones disponibles; por ejemplo, solo los inicios de sesión están disponibles cuando selecciona un propietario para un nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="fca30-105">Only available options appear; for instance, only logins are available when you are selecting an owner for a new object.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fca30-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="fca30-106">Options</span></span>  
 <span data-ttu-id="fca30-107">**Seleccionar estos tipos de objeto**</span><span class="sxs-lookup"><span data-stu-id="fca30-107">**Select these object types**</span></span>  
 <span data-ttu-id="fca30-108">Muestra una lista de los tipos a los que pertenecen los objetos que se van a seleccionar.</span><span class="sxs-lookup"><span data-stu-id="fca30-108">Displays a list of the types of which the objects to be selected belong.</span></span> <span data-ttu-id="fca30-109">Los tipos incluyen entidades de seguridad y elementos protegibles de nivel de base de datos y nivel de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fca30-109">The types include [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] level and database level principals and securables.</span></span> <span data-ttu-id="fca30-110">Este cuadro se llena con las selecciones efectuadas en el cuadro de diálogo **Seleccionar tipos de objetos** , al que se tiene acceso mediante el botón **Tipo de objeto** .</span><span class="sxs-lookup"><span data-stu-id="fca30-110">This box is populated from the selections made from the **Select Object Types** dialog box, accessed from the **Objects Type** button.</span></span>  
  
 <span data-ttu-id="fca30-111">**Escribir los nombres de objeto para seleccionar**</span><span class="sxs-lookup"><span data-stu-id="fca30-111">**Enter the object names to select**</span></span>  
 <span data-ttu-id="fca30-112">Escriba una lista, separada por puntos y comas, de los nombres de los objetos que se van a seleccionar.</span><span class="sxs-lookup"><span data-stu-id="fca30-112">Enter a semicolon-separated list of names of the objects to be selected.</span></span> <span data-ttu-id="fca30-113">Los objetos que se desea seleccionar deben ser de uno de los tipos que aparecen en la lista del cuadro **Seleccionar estos tipos de objeto** .</span><span class="sxs-lookup"><span data-stu-id="fca30-113">Objects to be selected must be of a type listed in the **Select these object types** box.</span></span> <span data-ttu-id="fca30-114">Los objetos se pueden seleccionar en una lista a la que se tiene acceso al hacer clic en el botón **Examinar** .</span><span class="sxs-lookup"><span data-stu-id="fca30-114">Objects can be selected from a list accessed by clicking the **Browse** button.</span></span>  
  
 <span data-ttu-id="fca30-115">**Tipos de objeto**</span><span class="sxs-lookup"><span data-stu-id="fca30-115">**Object Types**</span></span>  
 <span data-ttu-id="fca30-116">Muestra una lista de tipos de objeto.</span><span class="sxs-lookup"><span data-stu-id="fca30-116">Displays a list of object types.</span></span> <span data-ttu-id="fca30-117">Seleccione uno o más activando la casilla correspondiente al tipo.</span><span class="sxs-lookup"><span data-stu-id="fca30-117">Select one or more by selecting the check box corresponding to the type.</span></span>  
  
 <span data-ttu-id="fca30-118">**Comprobar nombres**</span><span class="sxs-lookup"><span data-stu-id="fca30-118">**Check Names**</span></span>  
 <span data-ttu-id="fca30-119">Valida los nombres de los objetos del cuadro **Escribir los nombres de objeto para seleccionar** .</span><span class="sxs-lookup"><span data-stu-id="fca30-119">Validates the object names in the **Enter the object names to select** box.</span></span> <span data-ttu-id="fca30-120">Si la lista presenta un nombre de objeto no válido, aparecerá el cuadro de diálogo **Nombre no encontrado** .</span><span class="sxs-lookup"><span data-stu-id="fca30-120">If an object name that is not valid is listed, the **Name not Found** dialog box is presented.</span></span> <span data-ttu-id="fca30-121">Mediante este cuadro de diálogo, el nombre se puede corregir o eliminar de la lista de objetos que se van a seleccionar.</span><span class="sxs-lookup"><span data-stu-id="fca30-121">With this dialog box, the name can be corrected or removed from the list of objects to select.</span></span>  
  
 <span data-ttu-id="fca30-122">**Browse**</span><span class="sxs-lookup"><span data-stu-id="fca30-122">**Browse**</span></span>  
 <span data-ttu-id="fca30-123">Presenta el cuadro de diálogo **Buscar objetos** .</span><span class="sxs-lookup"><span data-stu-id="fca30-123">Presents the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="fca30-124">Contiene una lista de objetos de los tipos que aparecen en la lista del cuadro **Seleccionar estos tipos de objeto** .</span><span class="sxs-lookup"><span data-stu-id="fca30-124">This contains a list of objects of the types listed in the **Select These Object Types** box.</span></span> <span data-ttu-id="fca30-125">Seleccione los objetos de esta lista activando las casillas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="fca30-125">Select objects from this list by selecting the corresponding check boxes.</span></span>  
  
  
