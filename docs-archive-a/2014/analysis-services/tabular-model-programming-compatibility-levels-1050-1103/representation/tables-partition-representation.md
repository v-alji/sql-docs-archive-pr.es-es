---
title: Representación de partición (tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: b606cd63-755c-4ac0-b19b-95b5363afbdf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6a29f273a584f3e60c6cf6458751965158cf8704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748940"
---
# <a name="partition-representation-tabular"></a><span data-ttu-id="fc163-102">Representación de partición (tabular)</span><span class="sxs-lookup"><span data-stu-id="fc163-102">Partition Representation (Tabular)</span></span>
  <span data-ttu-id="fc163-103">A efectos operativos, una tabla se puede dividir en distintos subconjuntos de filas que, al combinarse, forman la tabla. Cada uno de los subconjuntos es una partición de la tabla.</span><span class="sxs-lookup"><span data-stu-id="fc163-103">For operational purposes, a table can be divided in different subsets of rows that when combined together form the table; each of those subsets is a partition of the table.</span></span>  
  
## <a name="partition-representation"></a><span data-ttu-id="fc163-104">Representación de partición</span><span class="sxs-lookup"><span data-stu-id="fc163-104">Partition Representation</span></span>  
 <span data-ttu-id="fc163-105">Por lo que respecta a los objetos de AMO, las representaciones de particiones tienen una relación de asignación uno a uno con <xref:Microsoft.AnalysisServices.Partition> y no se necesitan otros objetos principales de AMO.</span><span class="sxs-lookup"><span data-stu-id="fc163-105">In terms of AMO objects a partition representation has a one to one mapping relationship with <xref:Microsoft.AnalysisServices.Partition> and no other main AMO objects are required</span></span>  
  
### <a name="partition-in-amo"></a><span data-ttu-id="fc163-106">Partición en AMO</span><span class="sxs-lookup"><span data-stu-id="fc163-106">Partition in AMO</span></span>  
 <span data-ttu-id="fc163-107">Cuando se usa AMO para administrar una partición, es necesario buscar el grupo de medida que representa la tabla modelo tabular y trabajar desde allí.</span><span class="sxs-lookup"><span data-stu-id="fc163-107">When using AMO to manage a partition in a you need to find the measure group that represents the Tabular Model table and work from there.</span></span>  
  
 <span data-ttu-id="fc163-108">En el fragmento de código siguiente se muestra cómo se agrega una partición a una tabla modelo existente.</span><span class="sxs-lookup"><span data-stu-id="fc163-108">The following code snippet shows how to add a partition to an existing tabular model table.</span></span>  
  
```  
  
private void AddPartition(  
                     AMO.Cube modelCube  
                  ,  AMO.DataSource newDatasource  
                  ,  string mgName  
                  ,  string newPartitionName  
                  , string partitionSelectStatement  
                  , Boolean processPartition  
             )  
{  
    mgName = mgName.Trim();  
    newPartitionName = newPartitionName.Trim();  
    partitionSelectStatement = partitionSelectStatement.Trim();  
    //Validate Input  
    if (string.IsNullOrEmpty(newPartitionName) || string.IsNullOrWhiteSpace(newPartitionName))  
    {  
        MessageBox.Show(String.Format("Partition Name cannot be empty or blank"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    if (modelCube.MeasureGroups[mgName].Partitions.ContainsName(newPartitionName))  
    {  
        MessageBox.Show(String.Format("Partition Name already defined. Duplicated names are not allowed"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    if (string.IsNullOrEmpty(partitionSelectStatement) || string.IsNullOrWhiteSpace(partitionSelectStatement))  
    {  
        MessageBox.Show(String.Format("Select statement cannot be empty or blank"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    //Input validated  
    string partitionID = newPartitionName; //Using partition name as the ID  
    AMO.Partition currentPartition = new AMO.Partition(partitionID, partitionID);  
    currentPartition.StorageMode = AMO.StorageMode.InMemory;  
    currentPartition.ProcessingMode = AMO.ProcessingMode.Regular;  
    currentPartition.Source = new AMO.QueryBinding(newDatasource.ID, partitionSelectStatement);  
    modelCube.MeasureGroups[mgName].Partitions.Add(currentPartition);  
    try  
    {  
        modelCube.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
        if (processPartition)  
        {  
            modelCube.MeasureGroups[mgName].Partitions[partitionID].Process(AMO.ProcessType.ProcessFull);  
            MessageBox.Show(String.Format("Partition successfully processed."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
        }  
  
    }  
    catch (AMO.AmoException amoXp)  
    {  
        MessageBox.Show(String.Format("AMO exception accessing the server.\nError message: {0}", amoXp.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Warning);  
        return;  
    }  
    catch (Exception)  
    {  
        throw;  
    }  
}  
  
```  
  
## <a name="amo2tabular-sample"></a><span data-ttu-id="fc163-109">Ejemplo AMO2Tabular</span><span class="sxs-lookup"><span data-stu-id="fc163-109">AMO2Tabular sample</span></span>  
 <span data-ttu-id="fc163-110">Sin embargo, para saber cómo usar AMO para crear y manipular representaciones de partición vea el código fuente del ejemplo AMO a tabular.</span><span class="sxs-lookup"><span data-stu-id="fc163-110">However, to have an understanding on how to use AMO to create and manipulate partition representations see the source code of the AMO to Tabular sample.</span></span> <span data-ttu-id="fc163-111">El ejemplo está disponible en Codeplex.</span><span class="sxs-lookup"><span data-stu-id="fc163-111">The sample is available at Codeplex.</span></span> <span data-ttu-id="fc163-112">Nota importante sobre el código: el código se proporciona solo como apoyo de los conceptos lógicos explicados aquí y no debe utilizarse en un entorno de producción; no debe usarse para otros fines excepto el pedagógico.</span><span class="sxs-lookup"><span data-stu-id="fc163-112">An important note about the code: the code is provided only as a support to the logical concepts explained here and should not be used in a production environment; nor should it be used for other purpose other than the pedagogical one.</span></span>  
  
  
