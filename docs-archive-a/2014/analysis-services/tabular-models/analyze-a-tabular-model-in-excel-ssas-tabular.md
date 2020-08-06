---
title: Analizar un modelo tabular en Excel (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.chooseperspect.f1
ms.assetid: 47fa45fc-60ab-41a1-bde3-5781c8462889
author: minewiskan
ms.author: owend
ms.openlocfilehash: fae542ffb5b470d23d9cf27fcc11367f571e7cec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675522"
---
# <a name="analyze-a-tabular-model-in-excel-ssas-tabular"></a><span data-ttu-id="49bc3-102">Analizar un modelo tabular en Excel (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="49bc3-102">Analyze a Tabular Model in Excel (SSAS Tabular)</span></span>
  <span data-ttu-id="49bc3-103">La característica Analizar en Excel de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] abre Microsoft Excel, crea una conexión de origen de datos con la base de datos del área de trabajo del modelo y agrega una tabla dinámica a la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="49bc3-103">The Analyze in Excel feature in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] opens Microsoft Excel, creates a data source connection to the model workspace database, and adds a PivotTable to the worksheet.</span></span> <span data-ttu-id="49bc3-104">Los objetos del modelo (tablas, columnas, medidas, jerarquías y KPI) se incluyen como campos en la lista de campos de la tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="49bc3-104">Model objects (tables, columns, measures, hierarchies, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49bc3-105">Para usar la característica Analizar en Excel, tiene que tener instalado Microsoft Office 2003 o posterior en el mismo equipo que [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49bc3-105">To use the Analyze in Excel feature, you must have Microsoft Office 2003 or later installed on the same computer as [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="49bc3-106">Si Office no está instalado en el mismo equipo, puede usar Excel en otro equipo y conectarse a la base de datos del área de trabajo del modelo como un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="49bc3-106">If Office is not installed on the same computer, you can use Excel on another computer and connect to the model workspace database as a data source.</span></span> <span data-ttu-id="49bc3-107">A continuación, podrá agregar manualmente una tabla dinámica a la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="49bc3-107">You can then manually add a PivotTable to the worksheet.</span></span> <span data-ttu-id="49bc3-108">Los objetos del modelo (tablas, columnas, medidas y KPI) se incluyen como campos en la lista de campos de la tabla dinámica.</span><span class="sxs-lookup"><span data-stu-id="49bc3-108">Model objects (tables, columns, measures, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="49bc3-109">Tareas</span><span class="sxs-lookup"><span data-stu-id="49bc3-109">Tasks</span></span>  
  
#### <a name="to-analyze-a-tabular-model-project-by-using-the-analyze-in-excel-feature"></a><span data-ttu-id="49bc3-110">Para analizar un proyecto de modelo tabular mediante la característica Analizar en Excel</span><span class="sxs-lookup"><span data-stu-id="49bc3-110">To analyze a tabular model project by using the Analyze in Excel feature</span></span>  
  
1.  <span data-ttu-id="49bc3-111">En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], haga clic en el menú **Modelo** y después en **Analizar en Excel**.</span><span class="sxs-lookup"><span data-stu-id="49bc3-111">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Analyze in Excel**.</span></span>  
  
2.  <span data-ttu-id="49bc3-112">En el cuadro de diálogo **Elegir credenciales y perspectivas** , seleccione una de las opciones de credenciales siguientes para conectarse al origen de datos del área de trabajo del modelo:</span><span class="sxs-lookup"><span data-stu-id="49bc3-112">In the **Choose Credential and Perspective** dialog box, select one of the following credential options to connect to the model workspace data source:</span></span>  
  
    -   <span data-ttu-id="49bc3-113">Para usar la cuenta de usuario actual, seleccione **Usuario de Windows actual**.</span><span class="sxs-lookup"><span data-stu-id="49bc3-113">To use the current user account, select **Current Windows User**.</span></span>  
  
    -   <span data-ttu-id="49bc3-114">Para usar una cuenta de usuario diferente, seleccione **Otro usuario de Windows**.</span><span class="sxs-lookup"><span data-stu-id="49bc3-114">To use a different user account, select **Other Windows User**.</span></span>  
  
         <span data-ttu-id="49bc3-115">Normalmente, esta cuenta de usuario será un miembro de un rol.</span><span class="sxs-lookup"><span data-stu-id="49bc3-115">Typically, this user account will be a member of a role.</span></span> <span data-ttu-id="49bc3-116">No se requiere una contraseña.</span><span class="sxs-lookup"><span data-stu-id="49bc3-116">No password is required.</span></span> <span data-ttu-id="49bc3-117">La cuenta solo se puede utilizar en el contexto de una conexión de Excel a la base de datos del área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="49bc3-117">The account can only be used in the context of an Excel connection to the workspace database.</span></span>  
  
    -   <span data-ttu-id="49bc3-118">Para usar un rol de seguridad, seleccione **Rol**y, a continuación, en el cuadro de lista, seleccione uno o varios roles.</span><span class="sxs-lookup"><span data-stu-id="49bc3-118">To use a security role, select **Role**, and then in the listbox, select one or more roles.</span></span>  
  
         <span data-ttu-id="49bc3-119">Los roles de seguridad se deben definir mediante el Administrador de roles.</span><span class="sxs-lookup"><span data-stu-id="49bc3-119">Security roles must be defined using the Role Manager.</span></span> <span data-ttu-id="49bc3-120">Para obtener más información, vea [Crear y administrar roles &#40;SSAS tabular&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="49bc3-120">For more information, see [Create and Manage Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
3.  <span data-ttu-id="49bc3-121">Para usar una perspectiva, seleccione una en el cuadro de lista **Perspectiva** .</span><span class="sxs-lookup"><span data-stu-id="49bc3-121">To use a perspective, in the **Perspective** listbox, select a perspective.</span></span>  
  
     <span data-ttu-id="49bc3-122">Las perspectivas (distintas de las predeterminadas) se deben definir mediante el cuadro de diálogo Perspectivas.</span><span class="sxs-lookup"><span data-stu-id="49bc3-122">Perspectives (other than default) must be defined using the Perspectives dialog box.</span></span> <span data-ttu-id="49bc3-123">Para obtener más información, vea [crear y administrar perspectivas &#40;&#41;tabular de SSAS ](perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="49bc3-123">For more information, see [Create and Manage Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49bc3-124">La lista de campos de tabla dinámica de Excel no se actualiza automáticamente a medida que se realizan cambios en el proyecto de modelos en el diseñador de modelos.</span><span class="sxs-lookup"><span data-stu-id="49bc3-124">The PivotTable Field List in Excel does not refresh automatically as you make changes to the model project in the model designer.</span></span> <span data-ttu-id="49bc3-125">Para actualizar dicha lista, en Excel, haga clic en **Actualizar** en la cinta **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="49bc3-125">To refresh the PivotTable Field List, in Excel, on the **Options** ribbon, click **Refresh**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49bc3-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49bc3-126">See Also</span></span>  
 [<span data-ttu-id="49bc3-127">Analizar en Excel &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="49bc3-127">Analyze in Excel &#40;SSAS Tabular&#41;</span></span>](analyze-in-excel-ssas-tabular.md)  
  
  
