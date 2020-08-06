---
title: Representación de perspectiva (tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 6d2636c4-dae4-448f-a1d4-dbee739e177c
author: minewiskan
ms.author: owend
ms.openlocfilehash: ca8a66d3134748fd524dc0c6b524d944213533e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671221"
---
# <a name="perspective-representation-tabular"></a><span data-ttu-id="e676a-102">Representación de perspectiva (tabular)</span><span class="sxs-lookup"><span data-stu-id="e676a-102">Perspective Representation (Tabular)</span></span>
  <span data-ttu-id="e676a-103">Una perspectiva es un mecanismo para simplificar o centrar el modelo en una parte menor de él para la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="e676a-103">A perspective is a mechanism to simplify or focus the model into a smaller portion of it for the client application.</span></span>  
  
 <span data-ttu-id="e676a-104">Consulte [representación de perspectiva (tabular)](perspective-representation-tabular.md) para obtener una explicación detallada sobre cómo crear y manipular la representación de perspectiva.</span><span class="sxs-lookup"><span data-stu-id="e676a-104">See [Perspective Representation (Tabular)](perspective-representation-tabular.md) for a detailed explanation on how to create and manipulate the perspective representation.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="e676a-105">Las perspectivas no son un mecanismo de seguridad. Se podrá tener acceso a los objetos que están fuera de la perspectiva mediante otras interfaces.</span><span class="sxs-lookup"><span data-stu-id="e676a-105">Perspectives are not a security mechanism; objects outside the perspective can still be accessed by the user through other interfaces.</span></span>  
  
## <a name="perspective-representation"></a><span data-ttu-id="e676a-106">Representación de perspectiva</span><span class="sxs-lookup"><span data-stu-id="e676a-106">Perspective Representation</span></span>  
 <span data-ttu-id="e676a-107">Por lo que respecta a los objetos de AMO, las representaciones de perspectivas tienen una relación de asignación uno a uno con <xref:Microsoft.AnalysisServices.Perspective> y no se necesitan otros objetos principales de AMO.</span><span class="sxs-lookup"><span data-stu-id="e676a-107">In terms of AMO objects a perspective representation has a one to one mapping relationship with <xref:Microsoft.AnalysisServices.Perspective> and no other main AMO objects are required.</span></span>  
  
### <a name="perspective-in-amo"></a><span data-ttu-id="e676a-108">Perspectiva de AMO</span><span class="sxs-lookup"><span data-stu-id="e676a-108">Perspective in AMO</span></span>  
 <span data-ttu-id="e676a-109">En el fragmento de código siguiente se muestra cómo se crea una perspectiva en un modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="e676a-109">The following code snippet shows how to create a perspective in a Tabular model.</span></span> <span data-ttu-id="e676a-110">El elemento clave de este fragmento de código es perspectiveElements. Este objeto es una representación gráfica de todos los objetos del modelo tabular que se exponen al usuario.</span><span class="sxs-lookup"><span data-stu-id="e676a-110">The key element in this piece of code is the perspectiveElements; this object is a graphical representation of all the objects in the tabular model that are exposed to the user.</span></span> <span data-ttu-id="e676a-111">*perspectiveElements* contiene 4 columnas y, en este escenario, solo son relevantes las columnas 1, 2 y 3.</span><span class="sxs-lookup"><span data-stu-id="e676a-111">*perspectiveElements* contains 4 columns and for this scenario only columns 1, 2 and 3 are relevant.</span></span> <span data-ttu-id="e676a-112">La columna 1 contiene el tipo de elemento mostrado - elementTypeValue-; la columna 2 contiene el nombre completo del elemento --, que probablemente tendrá que analizarse para poder incorporar el elemento en la perspectiva; la columna 3 contiene un elemento de casilla - checkedElement-, que indica si el elemento forma parte de la perspectiva o no.</span><span class="sxs-lookup"><span data-stu-id="e676a-112">Column 1 contains the type of element displayed -elementTypeValue-; column 2 contains the complete name of the element --, that probably will need to parsed to enter the element in the perspective; column 3 contains a checkbox item -checkedElement- that tells if the element is part of the perspective or not.</span></span>  
  
```  
  
private void updatePerspective_Click(  
                     AMO.Cube modelCube  
                  ,  DataGridView perspectiveElements  
                  ,  string updatedPerspectiveID  
             )  
{  
    //Update is done by delete first, create new and insert after  
    //if perspective doesn't exist then create first and insert after  
    updatedPerspectiveID = updatedPerspectiveID.Trim();  
    if (modelCube.Perspectives.Contains(updatedPerspectiveID))  
    {  
        modelCube.Perspectives.Remove(updatedPerspectiveID, true);  
        newDatabase.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
    }  
    AMO.Perspective currentPerspective = modelCube.Perspectives.Add(updatedPerspectiveID, updatedPerspectiveID);  
  
    foreach (DataGridViewRow currentDGVRow in perspectiveElements.Rows)  
    {  
        bool checkedElement = (bool)currentDGVRow.Cells[3].Value;  
        if (checkedElement)  
        {  
            string elementTypeValue = currentDGVRow.Cells[1].Value.ToString();  
            string elementNameValue = currentDGVRow.Cells[2].Value.ToString();  
            switch (elementTypeValue)  
            {  
                case "Column: Attribute":  
                case "Column: Calculated Column":  
                    {  
                        string perspectiveDimensionName = Regex.Match(elementNameValue, @"(?<=')(.*?)(?=')").ToString();  
                        string perspectiveDimensionAttributeName = Regex.Match(elementNameValue, @"(?<=\[)(.*?)(?=\])").ToString();  
                        AMO.PerspectiveDimension currentPerspectiveDimension;  
                        if (!currentPerspective.Dimensions.Contains(perspectiveDimensionName))  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions.Add(perspectiveDimensionName);  
                        }  
                        else  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions[perspectiveDimensionName];  
                        }  
                        if (!currentPerspectiveDimension.Attributes.Contains(perspectiveDimensionAttributeName))  
                        {  
                            currentPerspectiveDimension.Attributes.Add(perspectiveDimensionAttributeName);  
                        }  
                    }  
                    break;  
                case "Hierarchy":  
                    {  
                        string perspectiveDimensionName = Regex.Match(elementNameValue, @"(?<=')(.*?)(?=')").ToString();  
                        string perspectiveDimensionHierarchyName = Regex.Match(elementNameValue, @"(?<=\[)(.*?)(?=\])").ToString();  
                        AMO.PerspectiveDimension currentPerspectiveDimension;  
                        if (!currentPerspective.Dimensions.Contains(perspectiveDimensionName))  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions.Add(perspectiveDimensionName);  
                        }  
                        else  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions[perspectiveDimensionName];  
                        }  
                        if (!currentPerspectiveDimension.Hierarchies.Contains(perspectiveDimensionHierarchyName))  
                        {  
                            currentPerspectiveDimension.Hierarchies.Add(perspectiveDimensionHierarchyName);  
                        }  
                    }  
                    break;  
                case "Measure":  
                    {  
                        string perspectiveMeasureGroupName = Regex.Match(elementNameValue, @"(?<=')(.*?)(?=')").ToString();  
                        string measureName = Regex.Match(elementNameValue, @"(?<=\[)(.*?)(?=\])").ToString();  
                        string perspectiveMeasureName = string.Format("[Measures].[{0}]", measureName);  
                        AMO.PerspectiveCalculation currentPerspectiveCalculation = new AMO.PerspectiveCalculation(perspectiveMeasureName, AMO.PerspectiveCalculationType.Member);  
                        if (!currentPerspective.Calculations.Contains(perspectiveMeasureName))  
                        {  
                            currentPerspective.Calculations.Add(currentPerspectiveCalculation);  
                        }  
                        if (modelCube.MdxScripts["MdxScript"].CalculationProperties.Contains(string.Format("KPIs.[{0}]", measureName)))  
                        {//Current Measure is also a KPI ==> will be added to the KPIs collection of the perspective  
                            AMO.PerspectiveKpi currentPerspectiveKpi = new AMO.PerspectiveKpi(perspectiveMeasureName);  
                            if (!currentPerspective.Kpis.Contains(perspectiveMeasureName))  
                            {  
                                currentPerspective.Kpis.Add(currentPerspectiveKpi);  
                            }  
                        }  
                    }  
                    break;  
                default:  
                    break;  
            }  
        }  
    }  
  
    newDatabase.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.CreateOrReplace);  
    MessageBox.Show(String.Format("Perpective successfully updated."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
}  
  
```  
  
## <a name="amo2tabular-sample"></a><span data-ttu-id="e676a-113">Ejemplo AMO2Tabular</span><span class="sxs-lookup"><span data-stu-id="e676a-113">AMO2Tabular sample</span></span>  
 <span data-ttu-id="e676a-114">Sin embargo, para saber cómo usar AMO para crear y manipular representaciones de perspectiva vea el código fuente del ejemplo de AMO a tabular.</span><span class="sxs-lookup"><span data-stu-id="e676a-114">However, to have an understanding on how to use AMO to create and manipulate perspective representations see the source code of the AMO to Tabular sample.</span></span> <span data-ttu-id="e676a-115">El ejemplo está disponible en Codeplex.</span><span class="sxs-lookup"><span data-stu-id="e676a-115">The sample is available at Codeplex.</span></span> <span data-ttu-id="e676a-116">Nota importante sobre el código: el código se proporciona solo como apoyo de los conceptos lógicos explicados aquí y no debe utilizarse en un entorno de producción; no debe usarse para otros fines excepto el pedagógico.</span><span class="sxs-lookup"><span data-stu-id="e676a-116">An important note about the code: the code is provided only as a support to the logical concepts explained here and should not be used in a production environment; nor should it be used for other purpose other than the pedagogical one.</span></span>  
  
  
