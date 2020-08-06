---
title: Cuadro de diálogo Advertencias de validación (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65556
- vdt.dlgbox.validationwarnings
ms.assetid: fc76e234-ec9c-4a19-a65b-cb558ec8268e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4f94c3ae91e077af853db949847bc8448f6a4753
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673958"
---
# <a name="validation-warnings-dialog-box-visual-database-tools"></a><span data-ttu-id="0883a-102">Advertencias de validación (cuadro de diálogo, Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="0883a-102">Validation Warnings Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="0883a-103">Este cuadro de diálogo aparece si intenta guardar modificaciones que pueden producir efectos secundarios malintencionados o si es probable que se produzca un error en la operación de confirmación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0883a-103">This dialog box appears if you attempt to save modifications with potentially damaging side effects, or if the database commit operation is likely to fail.</span></span> <span data-ttu-id="0883a-104">Este cuadro de diálogo indica en qué pueden consistir estos efectos secundarios o por qué podría producirse un error en la operación de confirmación.</span><span class="sxs-lookup"><span data-stu-id="0883a-104">This dialog box indicates what those side effects might be or why the commit operation might fail.</span></span> <span data-ttu-id="0883a-105">Proporciona la opción de seguir con la modificación o cancelar la operación.</span><span class="sxs-lookup"><span data-stu-id="0883a-105">It gives you the chance to continue with the modification or cancel the operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0883a-106">Este cuadro de diálogo aparece al intentar transferir las modificaciones realizadas a la base de datos o al guardar un script de cambio.</span><span class="sxs-lookup"><span data-stu-id="0883a-106">This dialog box appears when you attempt to transmit your modifications to the database or when you save a change script.</span></span>  
  
 <span data-ttu-id="0883a-107">El cuadro de diálogo puede aparecer por cualquiera de estos motivos:</span><span class="sxs-lookup"><span data-stu-id="0883a-107">The dialog box can appear for any of these reasons:</span></span>  
  
-   <span data-ttu-id="0883a-108">Puede que no tenga permisos en la base de datos para confirmar todas las modificaciones.</span><span class="sxs-lookup"><span data-stu-id="0883a-108">You might not have database permissions to commit all the modifications.</span></span>  
  
-   <span data-ttu-id="0883a-109">Las modificaciones podrían producir restricciones CHECK, restricciones DEFAULT o columnas derivadas incorrectamente formadas.</span><span class="sxs-lookup"><span data-stu-id="0883a-109">Your modifications would result in improperly formed derived columns, default constraints, or check constraints.</span></span>  
  
-   <span data-ttu-id="0883a-110">Una modificación del tipo de datos de una columna podría ocasionar una pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="0883a-110">A modification to a column's data type might cause data loss.</span></span>  
  
-   <span data-ttu-id="0883a-111">Una modificación podría producir un índice de más de 900 bytes.</span><span class="sxs-lookup"><span data-stu-id="0883a-111">A modification would result in an index greater than 900 bytes.</span></span>  
  
-   <span data-ttu-id="0883a-112">Una modificación podría cambiar una tabla o columna que contribuye a una vista enlazada a un esquema o a una función definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="0883a-112">A modification would change a table or column contributing to a schema-bound view or user-defined function.</span></span>  
  
-   <span data-ttu-id="0883a-113">Una modificación podría hacer que se volviera a generar una tabla con uno o más desencadenadores cifrados; se quitarán los desencadenadores.</span><span class="sxs-lookup"><span data-stu-id="0883a-113">A modification would result in the re-creation of a table that has one or more encrypted triggers; the triggers will be dropped.</span></span>  
  
-   <span data-ttu-id="0883a-114">Las modificaciones producirían una configuración inusual de ANSI_NULLS o ANSI_PADDING, o ambos en las columnas de una tabla.</span><span class="sxs-lookup"><span data-stu-id="0883a-114">Your modifications will yield noteworthy settings of ANSI_NULLS or ANSI_PADDING or both for the columns within one table.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0883a-115">Opciones</span><span class="sxs-lookup"><span data-stu-id="0883a-115">Options</span></span>  
 <span data-ttu-id="0883a-116">**Sí**</span><span class="sxs-lookup"><span data-stu-id="0883a-116">**Yes**</span></span>  
 <span data-ttu-id="0883a-117">Se continua la operación para generar el script de cambio o transferir las modificaciones a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0883a-117">Proceed with the operation and generate the change script or transmit the modifications to the database.</span></span> <span data-ttu-id="0883a-118">La operación de confirmación puede generar errores si no tiene privilegios para modificar la base de datos, si las modificaciones realizadas producen un índice de más de 900 bytes o si dan lugar a restricciones CHECK, restricciones DEFAULT o columnas calculadas incorrectamente formadas.</span><span class="sxs-lookup"><span data-stu-id="0883a-118">The commit operation can still fail if you do not have privileges to modify the database, if your modifications will result in an index greater than 900 bytes, or if your modifications will result in an improperly formed computed column, default constraint, or check constraint.</span></span>  
  
 <span data-ttu-id="0883a-119">**No**</span><span class="sxs-lookup"><span data-stu-id="0883a-119">**No**</span></span>  
 <span data-ttu-id="0883a-120">Cancela la acción de guardar.</span><span class="sxs-lookup"><span data-stu-id="0883a-120">Cancel the save action.</span></span>  
  
 <span data-ttu-id="0883a-121">**Guardar archivo de texto**</span><span class="sxs-lookup"><span data-stu-id="0883a-121">**Save Text File**</span></span>  
 <span data-ttu-id="0883a-122">Muestra el cuadro de diálogo **Guardar como** , que permite especificar una ubicación para un archivo de texto que contiene una lista de advertencias.</span><span class="sxs-lookup"><span data-stu-id="0883a-122">Display the **Save As** dialog box, where you can specify a location for a text file containing a list of the warnings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0883a-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0883a-123">See Also</span></span>  
 <span data-ttu-id="0883a-124">[Diseñar tablas &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0883a-124">[Design Tables &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="0883a-125">Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="0883a-125">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
