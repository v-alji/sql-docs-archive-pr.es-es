---
title: Configurar un conjunto de campos predeterminado para informes de Power View (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- ql12.asvs.bidtoolset.deffieldset.f1
ms.assetid: 6836b42f-28b8-4a98-a86d-2c3c109f0189
author: minewiskan
ms.author: owend
ms.openlocfilehash: c66fbbacd0cc2efd7d379bcc8e68149551476869
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744354"
---
# <a name="configure-default-field-set-for-power-view-reports-ssas-tabular"></a><span data-ttu-id="c4610-102">Configurar un conjunto de campos predeterminado para informes de Power View (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="c4610-102">Configure Default Field Set for Power View Reports (SSAS Tabular)</span></span>
  <span data-ttu-id="c4610-103">Un conjunto de campos predeterminado es una lista predefinida de columnas y medidas que se agregan automáticamente a un lienzo de informe [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] cuando se selecciona la tabla en la lista de campos de informes.</span><span class="sxs-lookup"><span data-stu-id="c4610-103">A default field set is a predefined list of columns and measures that are automatically added to a [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] report canvas when the table is selected in the report field list.</span></span> <span data-ttu-id="c4610-104">Los autores de modelos tabulares pueden crear un conjunto de campos predeterminado para eliminar pasos redundantes para los autores de informes que usan el modelo en sus informes.</span><span class="sxs-lookup"><span data-stu-id="c4610-104">Tabular model authors can create a default field set to eliminate redundant steps for report authors who use the model for their reports.</span></span> <span data-ttu-id="c4610-105">Por ejemplo, si sabe que la mayoría de los autores del informe que trabajan con información de contacto del cliente siempre desean ver un nombre de contacto, un número del teléfono principal, una dirección de correo electrónico y un nombre de compañía, puede pre-seleccionar esas columnas para que siempre se agreguen al lienzo del informe cuando el autor haga clic en la tabla Customer Contact.</span><span class="sxs-lookup"><span data-stu-id="c4610-105">For example, if you know that most report authors who work with customer contact information always want to see a contact name, a primary phone number, an email address, and a company name, you can pre-select those columns so that they are always added to the report canvas when the author clicks the Customer Contact table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4610-106">Un conjunto de campos predeterminado solo se aplica a un modelo tabular utilizado como modelo de datos en [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4610-106">A default field set applies only to a tabular model used as a data model in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span> <span data-ttu-id="c4610-107">Los conjuntos de campos predeterminados no se admiten en los informes dinámicos de Excel.</span><span class="sxs-lookup"><span data-stu-id="c4610-107">Default field sets are not supported in Excel pivot reports.</span></span>  
  
## <a name="creating-a-default-field-set"></a><span data-ttu-id="c4610-108">Crear un conjunto de campos predeterminado</span><span class="sxs-lookup"><span data-stu-id="c4610-108">Creating a Default Field Set</span></span>  
 <span data-ttu-id="c4610-109">Puede determinar qué campos, si los hay, se incluirán de forma predeterminada cada vez que se seleccione una tabla específica en [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4610-109">You can determine which fields, if any, are included by default whenever a specific table is selected in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span> <span data-ttu-id="c4610-110">También puede determinar el orden en el que aparecen los campos en la lista.</span><span class="sxs-lookup"><span data-stu-id="c4610-110">You can also determine the order in which fields appear in the list.</span></span> <span data-ttu-id="c4610-111">Para especificar un conjunto de campos predeterminado, establezca las propiedades del proyecto de modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="c4610-111">To specify a default field set, you set report properties in the tabular model project.</span></span>  
  
#### <a name="to-add-a-default-field-set"></a><span data-ttu-id="c4610-112">Para agregar un conjunto de campos predeterminado</span><span class="sxs-lookup"><span data-stu-id="c4610-112">To add a default field set</span></span>  
  
1.  <span data-ttu-id="c4610-113">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], haga clic en la tabla (pestaña) para la que esté configurando una lista de campos predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c4610-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the table (tab) for which you are configuring a default field list.</span></span>  
  
2.  <span data-ttu-id="c4610-114">En la ventana **Propiedades** , en la propiedad **Conjunto de campos predeterminado** , haga clic en **Haga clic para editar**.</span><span class="sxs-lookup"><span data-stu-id="c4610-114">In the **Properties** window, in the **Default Field Set** property, click **Click to edit**.</span></span>  
  
3.  <span data-ttu-id="c4610-115">En el cuadro de diálogo Conjunto de campos predeterminado, seleccione uno o más campos.</span><span class="sxs-lookup"><span data-stu-id="c4610-115">In the Default Field Set dialog, select one or more fields.</span></span> <span data-ttu-id="c4610-116">Puede elegir cualquier campo de la tabla, incluidas las medidas.</span><span class="sxs-lookup"><span data-stu-id="c4610-116">You can choose any field in the table, including measures.</span></span> <span data-ttu-id="c4610-117">Mantenga presionada la tecla Mayús para seleccionar un rango, o la tecla Ctrl para seleccionar campos individuales.</span><span class="sxs-lookup"><span data-stu-id="c4610-117">Hold down the Shift key to select a range, or the Ctrl key to select individual fields.</span></span>  
  
4.  <span data-ttu-id="c4610-118">Haga clic en **Agregar** para agregarlos al conjunto de campos predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c4610-118">Click **Add** to add them to the default field set.</span></span>  
  
5.  <span data-ttu-id="c4610-119">Utilice los botones Arriba y Abajo para especificar un orden de la lista de campos.</span><span class="sxs-lookup"><span data-stu-id="c4610-119">Use the Up and Down buttons to specify an order to the field list.</span></span> <span data-ttu-id="c4610-120">Los campos se agregarán al informe en el orden definido para el conjunto de campos.</span><span class="sxs-lookup"><span data-stu-id="c4610-120">Fields will be added to the report in the order defined for the field set.</span></span>  
  
6.  <span data-ttu-id="c4610-121">Repita estos pasos para otras tablas del libro.</span><span class="sxs-lookup"><span data-stu-id="c4610-121">Repeat these steps for other tables in your workbook.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="c4610-122">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="c4610-122">Next Step</span></span>  
 <span data-ttu-id="c4610-123">Después de crear un conjunto de campos predeterminado, puede influir aún más en la experiencia de diseño de informes especificando etiquetas predeterminadas, imágenes predeterminadas, el comportamiento del grupo predeterminado o si las filas que contienen el mismo valor se agrupan en una fila o se enumeran individualmente.</span><span class="sxs-lookup"><span data-stu-id="c4610-123">After you create a default field set, you can further influence the report design experience by specifying default labels, default images, default group behavior, or whether rows that contain the same value are grouped together in one row or listed individually.</span></span> <span data-ttu-id="c4610-124">Para más información, vea [Configurar las propiedades de comportamiento de las tablas para informes de Power View &#40;SSAS tabular&#41;](power-view-configure-table-behavior-properties-for-reports.md).</span><span class="sxs-lookup"><span data-stu-id="c4610-124">For more information, see [Configure Table Behavior Properties for Power View Reports &#40;SSAS Tabular&#41;](power-view-configure-table-behavior-properties-for-reports.md).</span></span>  
  
  
