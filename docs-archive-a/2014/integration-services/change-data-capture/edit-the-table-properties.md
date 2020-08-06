---
title: Editar las propiedades de tabla | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- editTabProps
ms.assetid: 95ea72ba-8e40-4177-a963-0fb4d10c56e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1ba0809b99474704ec0e93e417a04d776bb26d9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670513"
---
# <a name="edit-the-table-properties"></a><span data-ttu-id="71b34-102">Editar las propiedades de tabla</span><span class="sxs-lookup"><span data-stu-id="71b34-102">Edit the Table Properties</span></span>
  <span data-ttu-id="71b34-103">Use este cuadro de diálogo para editar las columnas específicas de la tabla seleccionada donde se están capturando cambios.</span><span class="sxs-lookup"><span data-stu-id="71b34-103">Use this dialog box to edit the specific columns from the selected table where changes are being captured.</span></span> <span data-ttu-id="71b34-104">También puede editar la información de **Rol de seguridad** y de **Instancia de captura** .</span><span class="sxs-lookup"><span data-stu-id="71b34-104">You can also edit the **Security Role** and **Capture Instance** information.</span></span>  
  
### <a name="to-edit-the-columns-to-include-in-the-cdc-instance"></a><span data-ttu-id="71b34-105">Para editar las columnas que se van a incluir en la instancia CDC</span><span class="sxs-lookup"><span data-stu-id="71b34-105">To edit the columns to include in the CDC instance</span></span>  
  
1.  <span data-ttu-id="71b34-106">Realice una o ambas de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="71b34-106">Do one or both of the following:</span></span>  
  
    -   <span data-ttu-id="71b34-107">Active la casilla situada junto a cualquier columna adicional que desee incluir.</span><span class="sxs-lookup"><span data-stu-id="71b34-107">Select the check box next to any additional column you want to include.</span></span>  
  
    -   <span data-ttu-id="71b34-108">Desactive la casilla situada junto a cualquier columna que ya no desee incluir.</span><span class="sxs-lookup"><span data-stu-id="71b34-108">Clear the check box next to any column that you no longer want to include.</span></span>  
  
### <a name="to-edit-the-security-role"></a><span data-ttu-id="71b34-109">Para editar el rol de seguridad</span><span class="sxs-lookup"><span data-stu-id="71b34-109">To edit the Security Role</span></span>  
  
1.  <span data-ttu-id="71b34-110">Escriba un nuevo nombre o edite el nombre del rol de seguridad en el campo **Rol de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="71b34-110">Type a new name or edit the name of the security role in the **Security Role** field.</span></span>  
  
### <a name="to-create-a-new-capture-instance"></a><span data-ttu-id="71b34-111">Para crear una instancia de captura nueva</span><span class="sxs-lookup"><span data-stu-id="71b34-111">To create a new capture instance</span></span>  
  
1.  <span data-ttu-id="71b34-112">En la sección **Rol de seguridad** , en el campo **Nombre** , escriba un nombre para la instancia de captura.</span><span class="sxs-lookup"><span data-stu-id="71b34-112">In the **Security Role** section, **Name** field enter a name for the capture instance.</span></span> <span data-ttu-id="71b34-113">De forma predeterminada, el nombre especificado en el campo es el nombre de la instancia de captura actual al final del cual se ha agregado **_NEW** (por ejemplo, **instancia_anterior_NEW**).</span><span class="sxs-lookup"><span data-stu-id="71b34-113">By default, the name entered in the field is the name of the current capture instance with **_NEW** added to the end of the name (for example, **old_instance_NEW**).</span></span>  
  
2.  <span data-ttu-id="71b34-114">Guarde la instancia de captura de una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="71b34-114">Save the capture instance as one of the following:</span></span>  
  
    -   <span data-ttu-id="71b34-115">**Nueva instancia de captura**: en este caso se guarda una nueva instancia de captura y la antigua instancia de captura no se elimina.</span><span class="sxs-lookup"><span data-stu-id="71b34-115">**New Capture Instance**: In this case a new capture instance is saved and the old capture instance is not deleted.</span></span>  
  
         <span data-ttu-id="71b34-116">**Nota**: no puede tener más de dos instancias de captura por tabla.</span><span class="sxs-lookup"><span data-stu-id="71b34-116">**Note**: You can have no more than two capture instances per table.</span></span> <span data-ttu-id="71b34-117">Si ya hay dos instancias de captura, esta opción no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="71b34-117">If there are already two capture instances, this option is not available.</span></span>  
  
    -   <span data-ttu-id="71b34-118">**Reemplazar existente**: en este caso, la instancia de captura actual se elimina y se reemplaza con la instancia de captura que ha creado.</span><span class="sxs-lookup"><span data-stu-id="71b34-118">**Replace Existing**: In this case the current capture instance is deleted and replaced by the capture instance you created.</span></span> <span data-ttu-id="71b34-119">Si hay dos instancias de captura definidas para esta tabla, debe seleccionar una para reemplazar.</span><span class="sxs-lookup"><span data-stu-id="71b34-119">If there are two capture instances defined for this table, you must select one to replace.</span></span>  
  
 <span data-ttu-id="71b34-120">**Nota**: puede quitar una instancia de captura de la lista de tablas en la pestaña **Tabla** .</span><span class="sxs-lookup"><span data-stu-id="71b34-120">**Note**: You can remove a capture instance from the list of tables in the **Table** tab.</span></span>  
  
 <span data-ttu-id="71b34-121">Cuando termine de especificar la información en este cuadro de diálogo, haga clic en **Aceptar** para aceptar los cambios.</span><span class="sxs-lookup"><span data-stu-id="71b34-121">After you finish entering the information in this dialog box, click **OK** to accept the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b34-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71b34-122">See Also</span></span>  
 <span data-ttu-id="71b34-123">[Cómo editar las propiedades de la instancia CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="71b34-123">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="71b34-124">Realice los cambios en las tablas seleccionadas para capturar cambios </span><span class="sxs-lookup"><span data-stu-id="71b34-124">Make Changes to the Tables Selected for Capturing Changes</span></span>](make-changes-to-the-tables-selected-for-capturing-changes.md)  
  
  
