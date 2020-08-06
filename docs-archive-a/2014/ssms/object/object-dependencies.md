---
title: Dependencias del objeto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.objectdependencies.f1
ms.assetid: c63d1160-3f3d-45df-99be-6fe081125fb5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13d1775f1e4e6885fe56a43ce40c4ac155c5b361
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750437"
---
# <a name="object-dependencies"></a><span data-ttu-id="2d912-102">Dependencias del objeto</span><span class="sxs-lookup"><span data-stu-id="2d912-102">Object Dependencies</span></span>
  <span data-ttu-id="2d912-103">Algunos objetos de base de datos dependen de otros objetos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2d912-103">Some database objects have dependencies upon other database objects.</span></span> <span data-ttu-id="2d912-104">Por ejemplo, las vistas y los procedimientos almacenados dependen de la existencia de tablas que contengan los datos devueltos por la vista o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2d912-104">For example, views and stored procedures depend upon the existence of tables that contain the data returned by the view or procedure.</span></span> <span data-ttu-id="2d912-105">En la página general de **Dependencias del objeto (página General)** del objeto actual se indican los objetos de la base de datos que deben estar presentes para que el objeto funcione correctamente, así como los objetos que dependen del objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2d912-105">The **Object Dependencies (General Page)** for the current object lists both the database objects that must be present for the object to function properly and the objects that depend upon the selected object.</span></span> <span data-ttu-id="2d912-106">Un objeto que hace referencia a otro objeto en su definición y esa definición se almacena en el catálogo del sistema se denomina una *entidad de referencia*.</span><span class="sxs-lookup"><span data-stu-id="2d912-106">An object that references another object in its definition and that definition is stored in the system catalog is called a *referencing entity*.</span></span> <span data-ttu-id="2d912-107">Un objeto al que se hace referencia por otro objeto se denomina una *entidad a la que se hace referencia*.</span><span class="sxs-lookup"><span data-stu-id="2d912-107">An object that is referred to by another object is called a *referenced entity*.</span></span>  
  
 <span data-ttu-id="2d912-108">**Dependencias del objeto (página Opciones avanzadas)** para el objeto actual contiene una lista de los objetos de base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y los objetos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que dependen del objeto.</span><span class="sxs-lookup"><span data-stu-id="2d912-108">The **Object Dependencies (Advanced Page)** for the current object lists the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database objects and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] objects that depend on the object.</span></span> <span data-ttu-id="2d912-109">Los objetos pueden estar almacenados en servidores diferentes.</span><span class="sxs-lookup"><span data-stu-id="2d912-109">The objects may be stored on different servers.</span></span>  
  
 <span data-ttu-id="2d912-110">Use este cuadro de diálogo para saber qué dependencias existen antes de cambiar o eliminar el objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2d912-110">Use this dialog box to understand the dependencies before changing or deleting the selected object.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2d912-111">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="2d912-111">UI element list</span></span>  
 <span data-ttu-id="2d912-112">**Objetos que dependen de**  _\<selected object>_</span><span class="sxs-lookup"><span data-stu-id="2d912-112">**Objects that depend on**  _\<selected object>_</span></span>  
 <span data-ttu-id="2d912-113">Haga clic en este botón para mostrar una lista de los objetos de cuyas dependencias se realiza un seguimiento y que dependen del objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2d912-113">Clicking this button displays a list of those objects that are dependency-tracked and that depend on the selected object.</span></span>  
  
 <span data-ttu-id="2d912-114">**Objetos en los que** _\<selected object>_ **depende**    </span><span class="sxs-lookup"><span data-stu-id="2d912-114">**Objects on which**  _\<selected object>_  **depends**</span></span>  
 <span data-ttu-id="2d912-115">Haga clic en este botón para mostrar una lista de los objetos de cuyas dependencias se realiza un seguimiento y de los que depende el objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2d912-115">Clicking this button displays a list of those objects that are dependency-tracked, on which the selected object depends.</span></span>  
  
 <span data-ttu-id="2d912-116">**Dependencias**</span><span class="sxs-lookup"><span data-stu-id="2d912-116">**Dependencies**</span></span>  
 <span data-ttu-id="2d912-117">Si se hace clic en **Objetos que dependen de** _\<selected object>_ , aquí se muestra una vista jerárquica de los objetos que dependen del objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2d912-117">If **Objects that depend on** _\<selected object>_ is clicked, this displays an hierarchical view of objects that depend on the selected object.</span></span> <span data-ttu-id="2d912-118">Si se hace clic en **Objetos de los que** _\<selected object>_ **depende**, se muestra una vista jerárquica objetos de los cuales depende el objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2d912-118">If **Objects on which** _\<selected object>_ **depends** is clicked, this displays an hierarchical view of objects on which the selected object depends.</span></span>  
  
 <span data-ttu-id="2d912-119">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="2d912-119">**Name**</span></span>  
 <span data-ttu-id="2d912-120">Muestra el nombre del objeto seleccionado en la vista de árbol **Dependencias** anterior.</span><span class="sxs-lookup"><span data-stu-id="2d912-120">Displays the name of the object selected in the **Dependencies** tree view above.</span></span>  
  
 <span data-ttu-id="2d912-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2d912-121">**Type**</span></span>  
 <span data-ttu-id="2d912-122">Muestra el tipo del objeto seleccionado en la vista de árbol **Dependencias** anterior.</span><span class="sxs-lookup"><span data-stu-id="2d912-122">Displays the type of the object selected in the **Dependencies** tree view above.</span></span>  
  
 <span data-ttu-id="2d912-123">**Hora de última sincronización**</span><span class="sxs-lookup"><span data-stu-id="2d912-123">**Last Sync Time**</span></span>  
 > [!NOTE]  
>  <span data-ttu-id="2d912-124">Esta opción solo está disponible en la página **Opciones avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="2d912-124">This option is available only on the **Advanced** page.</span></span>  
  
 <span data-ttu-id="2d912-125">Especifica la fecha y hora en que se actualizó por última vez la información de dependencias.</span><span class="sxs-lookup"><span data-stu-id="2d912-125">Specifies the time and date when the dependency information was last updated.</span></span>  
  
 <span data-ttu-id="2d912-126">**Tipo de dependencia**</span><span class="sxs-lookup"><span data-stu-id="2d912-126">**Dependency type**</span></span>  
 > [!NOTE]  
>  <span data-ttu-id="2d912-127">Esta opción solo está disponible en la página **General** .</span><span class="sxs-lookup"><span data-stu-id="2d912-127">This option is available only on the **General** page.</span></span>  
  
 <span data-ttu-id="2d912-128">Muestra el tipo de dependencia entre dos objetos.</span><span class="sxs-lookup"><span data-stu-id="2d912-128">Displays the type of dependency between two objects.</span></span> <span data-ttu-id="2d912-129">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2d912-129">Can be one of the following:</span></span>  
  
-   <span data-ttu-id="2d912-130">Dependencia enlazada a esquema</span><span class="sxs-lookup"><span data-stu-id="2d912-130">Schema-bound dependency</span></span>  
  
     <span data-ttu-id="2d912-131">Es una relación entre dos objetos que evita que el objeto referenciado se elimine o modifique mientras el objeto que realiza la referencia exista.</span><span class="sxs-lookup"><span data-stu-id="2d912-131">Is a relationship between two objects that prevents the referenced object from being dropped or modified as long as the referencing object exists.</span></span> <span data-ttu-id="2d912-132">Se crea una Dependencia enlazada a esquema cuando una vista o función definida por el usuario se crea utilizando la cláusula WITH SCHEMABINDING o cuando una tabla hace referencia a otro objeto a través de una restricción CHECK o DEFAULT, o bien en la definición de una columna calculada.</span><span class="sxs-lookup"><span data-stu-id="2d912-132">A schema-bound dependency is created when a view or user-defined function is created by using the WITH SCHEMABINDING clause, or when a table references another object through a CHECK or DEFAULT constraint or in the definition of a computed column.</span></span>  
  
-   <span data-ttu-id="2d912-133">Dependencia no enlazada a esquema</span><span class="sxs-lookup"><span data-stu-id="2d912-133">Non-schema-bound dependency</span></span>  
  
     <span data-ttu-id="2d912-134">Es una relación entre dos objetos que no evita que el objeto referenciado se elimine o modifique.</span><span class="sxs-lookup"><span data-stu-id="2d912-134">Is a relationship between two objects that does not prevent the referenced object from being dropped or modified.</span></span>  
  
-   <span data-ttu-id="2d912-135">Entidad no disponible o sin resolver</span><span class="sxs-lookup"><span data-stu-id="2d912-135">Not available or Unresolved Entity</span></span>  
  
     <span data-ttu-id="2d912-136">Indica que no se puede determinar el tipo de dependencia.</span><span class="sxs-lookup"><span data-stu-id="2d912-136">Indicates the dependency type cannot be determined.</span></span> <span data-ttu-id="2d912-137">Esta situación solo puede producirse cuando el objeto seleccionado está en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que es anterior a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d912-137">This occurs only when the selected object is on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
  
