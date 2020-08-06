---
title: Eliminar objetos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.deleteobjects.f1
helpviewer_keywords:
- Delete Objects dialog box
ms.assetid: 49541441-179c-40d3-ba0c-01bcae545984
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7b20d1eee3e48c5531b6b788e125b943f7606d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661784"
---
# <a name="delete-objects"></a><span data-ttu-id="2f2e3-102">Eliminar objetos</span><span class="sxs-lookup"><span data-stu-id="2f2e3-102">Delete Objects</span></span>
  <span data-ttu-id="2f2e3-103">Utilice este cuadro de diálogo para eliminar una base de datos de un objeto de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f2e3-103">Use this dialog box to delete a database or database object.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2f2e3-104">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="2f2e3-104">UI element list</span></span>  
 <span data-ttu-id="2f2e3-105">**Objeto que se va a eliminar**</span><span class="sxs-lookup"><span data-stu-id="2f2e3-105">**Object to be deleted**</span></span>  
 <span data-ttu-id="2f2e3-106">Muestra los nombres, tipos, propietarios y estado de los objetos que van a eliminarse, así como los mensajes de error generados durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="2f2e3-106">Displays the names, types, owners, and status of the objects that are about to be deleted, as well as any messages about errors during execution.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f2e3-107">La ejecución de **Eliminar** en una base de datos equivale a enviar DROP DATABASE en [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f2e3-107">Running **Delete** on a database is equivalent to issuing DROP DATABASE in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2f2e3-108">**Mostrar dependencias**</span><span class="sxs-lookup"><span data-stu-id="2f2e3-108">**Show Dependencies**</span></span>  
 <span data-ttu-id="2f2e3-109">Haga clic para mostrar los objetos que dependen del objeto actualmente seleccionado y de los cuales éste depende (dependencia ascendente y descendente).</span><span class="sxs-lookup"><span data-stu-id="2f2e3-109">Click to display both the objects that are dependent on the currently selected object and objects that the current object is dependent on (upward and downward dependency).</span></span> <span data-ttu-id="2f2e3-110">La información que aparece en el cuadro de diálogo **Mostrar dependencias** es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="2f2e3-110">The information displayed in the **Show Dependencies** dialog box is read-only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f2e3-111">El botón **Mostrar dependencias** no aparece para todos los tipos de objetos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f2e3-111">The **Show Dependencies** button does not appear for all types of database objects.</span></span> <span data-ttu-id="2f2e3-112">Para ver las dependencias cuando el botón **Mostrar dependencias** no está disponible, haga clic con el botón derecho en el objeto en el Explorador de objetos y luego haga clic en **Ver dependencias**.</span><span class="sxs-lookup"><span data-stu-id="2f2e3-112">To view dependencies when the **Show Dependencies** button is not available, right-click the object in Object Explorer, and then click **View Dependencies**.</span></span>  
  
 <span data-ttu-id="2f2e3-113">**Eliminar la información del historial de copia de seguridad y restauración para las bases de datos**</span><span class="sxs-lookup"><span data-stu-id="2f2e3-113">**Delete backup and restore history information for databases**</span></span>  
 <span data-ttu-id="2f2e3-114">Solo aparece cuando se elimina una base de datos; esta casilla hace que el historial de copias de seguridad y restauración de la base de datos se elimine de la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="2f2e3-114">Only appears when a database is deleted, this check box causes the backup and restore history for the subject database to be deleted from the **msdb** database.</span></span>  
  
 <span data-ttu-id="2f2e3-115">**Cerrar conexiones existentes**</span><span class="sxs-lookup"><span data-stu-id="2f2e3-115">**Close existing connections**</span></span>  
 <span data-ttu-id="2f2e3-116">Solo aparece cuando se elimina una base de datos; esta casilla termina las conexiones a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f2e3-116">Only appears when a database is deleted, this check box terminates connections to the subject database.</span></span>  
  
  
