---
title: Opciones de atributos fijos y variables (Asistente para dimensiones de variación lenta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.attriboption.f1
ms.assetid: c841345c-7d03-452f-9379-1c8c464f029c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df654cd97b343179828ebd94dea40eacc90e003d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669771"
---
# <a name="fixed-and-changing-attribute-options-slowly-changing-dimension-wizard"></a><span data-ttu-id="eafda-102">Opciones de atributos fijos y variables (Asistente para dimensiones variables)</span><span class="sxs-lookup"><span data-stu-id="eafda-102">Fixed and Changing Attribute Options (Slowly Changing Dimension Wizard</span></span>
  <span data-ttu-id="eafda-103">Utilice el cuadro de diálogo **Opciones de atributos fijos y variables** para especificar cómo se debe responder a los cambios realizados en los atributos fijos y variables.</span><span class="sxs-lookup"><span data-stu-id="eafda-103">Use the **Fixed and Changing Attribute Options** dialog box to specify how to respond to changes in fixed and changing attributes.</span></span>  
  
 <span data-ttu-id="eafda-104">Para obtener más información acerca de este asistente, vea [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="eafda-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="eafda-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="eafda-105">Options</span></span>  
 <span data-ttu-id="eafda-106">**Atributos fijos**</span><span class="sxs-lookup"><span data-stu-id="eafda-106">**Fixed attributes**</span></span>  
 <span data-ttu-id="eafda-107">En el caso de los atributos fijos, indique si la tarea debe dar un error cuando se detecte un cambio en un atributo fijo.</span><span class="sxs-lookup"><span data-stu-id="eafda-107">For fixed attributes, indicate whether the task should fail if a change is detected in a fixed attribute.</span></span>  
  
 <span data-ttu-id="eafda-108">**Atributos variables**</span><span class="sxs-lookup"><span data-stu-id="eafda-108">**Changing attributes**</span></span>  
 <span data-ttu-id="eafda-109">En el caso de los atributos variables, indique si la tarea debe cambiar todos los registros no actualizados o expirados, además de los actuales, cuando se detecten cambios en un atributo variable.</span><span class="sxs-lookup"><span data-stu-id="eafda-109">For changing attributes, indicate whether the task should change outdated or expired records, in addition to current records, when a change is detected in a changing attribute.</span></span> <span data-ttu-id="eafda-110">Los registros expirados son los que se han reemplazado por uno nuevo mediante un cambio en un atributo histórico (un cambio del Tipo 2).</span><span class="sxs-lookup"><span data-stu-id="eafda-110">An expired record is a record that has been replaced with a newer record by a change in a historical attribute (a Type 2 change).</span></span> <span data-ttu-id="eafda-111">La selección de esta opción puede imponer requisitos adicionales de procesamiento en un objeto multidimensional generado en el almacenamiento de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="eafda-111">Selecting this option may impose additional processing requirements on a multidimensional object constructed on the relational data warehouse.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eafda-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eafda-112">See Also</span></span>  
 [<span data-ttu-id="eafda-113">Configuración de salidas con el Asistente para dimensiones de variación lenta</span><span class="sxs-lookup"><span data-stu-id="eafda-113">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
