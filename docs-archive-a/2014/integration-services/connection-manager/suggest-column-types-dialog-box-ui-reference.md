---
title: Referencia de la interfaz de usuario del cuadro de diálogo Sugerir tipos de columna | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.suggestdatatypes.f1
ms.assetid: 8d5652e0-cf57-483f-828b-10f00c08418b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cbca2a3186a58b1148eb9627825fdfddf334339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750078"
---
# <a name="suggest-column-types-dialog-box-ui-reference"></a><span data-ttu-id="f5a4e-102">Referencia de la interfaz de usuario del cuadro de diálogo Sugerir tipos de columna</span><span class="sxs-lookup"><span data-stu-id="f5a4e-102">Suggest Column Types Dialog Box UI Reference</span></span>
  <span data-ttu-id="f5a4e-103">Utilice el cuadro de diálogo **Sugerir tipos de columna** para identificar el tipo de datos y la longitud de las columnas de un Administrador de conexiones de archivos planos basándose en un muestreo del contenido del archivo.</span><span class="sxs-lookup"><span data-stu-id="f5a4e-103">Use the **Suggest Column Types** dialog box to identify the data type and length of columns in a Flat File Connection Manager based on a sampling of the file content.</span></span>  
  
 <span data-ttu-id="f5a4e-104">Para obtener más información sobre los tipos de datos que usa [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], vea [Tipos de datos de Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="f5a4e-104">To learn more about the data types used by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f5a4e-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="f5a4e-105">Options</span></span>  
 <span data-ttu-id="f5a4e-106">**Número de filas**</span><span class="sxs-lookup"><span data-stu-id="f5a4e-106">**Number of rows**</span></span>  
 <span data-ttu-id="f5a4e-107">Escriba o seleccione el número de filas de la muestra que utiliza el algoritmo.</span><span class="sxs-lookup"><span data-stu-id="f5a4e-107">Type or select the number of rows in the sample that the algorithm uses.</span></span>  
  
 <span data-ttu-id="f5a4e-108">**Sugerir el tipo de datos entero más pequeño**</span><span class="sxs-lookup"><span data-stu-id="f5a4e-108">**Suggest the smallest integer data type**</span></span>  
 <span data-ttu-id="f5a4e-109">Desactive esta casilla para omitir la evaluación.</span><span class="sxs-lookup"><span data-stu-id="f5a4e-109">Clear this check box to skip the assessment.</span></span> <span data-ttu-id="f5a4e-110">Si está activada, determina el tipo de datos entero más pequeño posible en columnas que contienen datos numéricos integrales.</span><span class="sxs-lookup"><span data-stu-id="f5a4e-110">If selected, determines the smallest possible integer data type for columns that contain integral numeric data.</span></span>  
  
 <span data-ttu-id="f5a4e-111">**Sugerir el tipo de datos real más pequeño**</span><span class="sxs-lookup"><span data-stu-id="f5a4e-111">**Suggest the smallest real data type**</span></span>  
 <span data-ttu-id="f5a4e-112">Desactive esta casilla para omitir la evaluación.</span><span class="sxs-lookup"><span data-stu-id="f5a4e-112">Clear this check box to skip the assessment.</span></span> <span data-ttu-id="f5a4e-113">Si está activada, determina si las columnas que contienen datos numéricos reales pueden utilizar el tipo de datos real más pequeño, DT_R4.</span><span class="sxs-lookup"><span data-stu-id="f5a4e-113">If selected, determines whether columns that contain real numeric data can use the smaller real data type, DT_R4.</span></span>  
  
 <span data-ttu-id="f5a4e-114">**Identificar columnas booleanas mediante los valores siguientes**</span><span class="sxs-lookup"><span data-stu-id="f5a4e-114">**Identify Boolean columns using the following values**</span></span>  
 <span data-ttu-id="f5a4e-115">Escriba los dos valores que desea utilizar como valores booleanos True y False.</span><span class="sxs-lookup"><span data-stu-id="f5a4e-115">Type the two values that you want to use as the Boolean values true and false.</span></span> <span data-ttu-id="f5a4e-116">Los valores deben aparecer separados con una coma; el primer valor representa True.</span><span class="sxs-lookup"><span data-stu-id="f5a4e-116">The values must be separated by a comma, and the first value represents True.</span></span>  
  
 <span data-ttu-id="f5a4e-117">**Rellenar columnas de cadena**</span><span class="sxs-lookup"><span data-stu-id="f5a4e-117">**Pad string columns**</span></span>  
 <span data-ttu-id="f5a4e-118">Active esta casilla para habilitar el relleno de cadenas.</span><span class="sxs-lookup"><span data-stu-id="f5a4e-118">Select this check box to enable string padding.</span></span>  
  
 <span data-ttu-id="f5a4e-119">**Porcentaje de relleno**</span><span class="sxs-lookup"><span data-stu-id="f5a4e-119">**Percent padding**</span></span>  
 <span data-ttu-id="f5a4e-120">Escriba o seleccione el porcentaje de longitud de columna que se incrementará para tipos de datos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f5a4e-120">Type or select the percentage of the column lengths by which to increase the length of columns for character data types.</span></span> <span data-ttu-id="f5a4e-121">El porcentaje debe ser un número entero.</span><span class="sxs-lookup"><span data-stu-id="f5a4e-121">The percentage must be an integer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a4e-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f5a4e-122">See Also</span></span>  
 <span data-ttu-id="f5a4e-123">[Referencia de errores y mensajes de Integration Services](../integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f5a4e-123">[Integration Services Error and Message Reference](../integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="f5a4e-124">Administrador de conexiones de archivos planos</span><span class="sxs-lookup"><span data-stu-id="f5a4e-124">Flat File Connection Manager</span></span>](file-connection-manager.md)  
  
  
