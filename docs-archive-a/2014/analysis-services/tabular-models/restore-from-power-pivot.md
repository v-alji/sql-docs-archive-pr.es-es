---
title: Restaurar desde PowerPivot | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql11.asvs.ssmsimbi.RestoreFromPP.f1
ms.assetid: 232ac8ed-77fe-47d8-acd3-59bc2fdfdf48
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dbb0e7867451e67eaa1503c54d7e3da1c276965
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748939"
---
# <a name="restore-from-powerpivot"></a><span data-ttu-id="a56f3-102">Restaurar desde PowerPivot</span><span class="sxs-lookup"><span data-stu-id="a56f3-102">Restore from PowerPivot</span></span>
  <span data-ttu-id="a56f3-103">Puede utilizar la característica Restaurar desde PowerPivot en SQL Server Management Studio para crear una nueva base de datos de modelos tabulares en una instancia de Analysis Services (ejecutándose en modo tabular), o para llevar a cabo la restauración en una base de datos existente desde un libro PowerPivot (.xlsx).</span><span class="sxs-lookup"><span data-stu-id="a56f3-103">You can use the Restore from PowerPivot feature in SQL Server Management Studio to create a new Tabular model database on an Analysis Services instance (running in Tabular mode), or restore to an existing database from a PowerPivot workbook (.xlsx).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a56f3-104">La plantilla de proyecto Importar desde PowerPivot de SQL Server Data Tools proporciona una funcionalidad similar.</span><span class="sxs-lookup"><span data-stu-id="a56f3-104">The Import from PowerPivot project template in SQL Server Data Tools provides similar functionality.</span></span> <span data-ttu-id="a56f3-105">Para obtener más información, vea [Importar desde PowerPivot &#40;&#41;tabular de SSAS ](import-from-power-pivot-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="a56f3-105">For more information, see [Import from PowerPivot &#40;SSAS Tabular&#41;](import-from-power-pivot-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="a56f3-106">Al utilizar la característica Restaurar desde PowerPivot, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a56f3-106">When using Restore from PowerPivot, keep the following in mind:</span></span>  
  
-   <span data-ttu-id="a56f3-107">Para utilizar la restauración desde PowerPivot, es necesario haber iniciado sesión como miembro del rol de administrador del servidor en la instancia de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a56f3-107">In order to use Restore from PowerPivot, you must be logged on as a member of the Server Administrators role on the Analysis Services instance.</span></span>  
  
-   <span data-ttu-id="a56f3-108">La cuenta de servicio de la instancia de Analysis Services debe tener permisos de lectura en el archivo de libro desde el que va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="a56f3-108">The Analysis Services instance service account must have Read permissions on the workbook file you are restoring from.</span></span>  
  
-   <span data-ttu-id="a56f3-109">De forma predeterminada, cuando se restaura una base de datos desde PowerPivot, la propiedad Información de suplantación de origen de datos de la base de datos de modelos tabulares se establece en Predeterminado, que especifica la cuenta de servicio de la instancia de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a56f3-109">By default, when you restore a database from PowerPivot, the Tabular model database Data Source Impersonation Info property is set to Default, which specifies the Analysis Services instance service account.</span></span> <span data-ttu-id="a56f3-110">Se recomienda cambiar las credenciales de suplantación a una cuenta de usuario de Windows en Propiedades de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a56f3-110">It is recommended you change the impersonation credentials to a Windows user account in Database Properties.</span></span> <span data-ttu-id="a56f3-111">Para más información, vea [Suplantación &#40;SSAS tabular&#41;](impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="a56f3-111">For more information, see [Impersonation &#40;SSAS Tabular&#41;](impersonation-ssas-tabular.md).</span></span>  
  
-   <span data-ttu-id="a56f3-112">Los datos del modelo de datos de PowerPivot se copiarán en una base de datos de modelos tabulares nueva o en una ya existente en la instancia de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a56f3-112">Data in the PowerPivot data model will be copied into an existing or new Tabular model database on the Analysis Services instance.</span></span> <span data-ttu-id="a56f3-113">Si el libro PowerPivot contiene tablas vinculadas, estas se volverán a crear como una tabla sin un origen de datos, de forma similar a una tabla creada mediante Pegar en nueva tabla.</span><span class="sxs-lookup"><span data-stu-id="a56f3-113">If your PowerPivot workbook contains linked tables, they will be recreated as a table without a data source, similar to a table created using Paste To New table.</span></span>  
  
### <a name="to-restore-from-powerpivot"></a><span data-ttu-id="a56f3-114">Para restaurar desde PowerPivot</span><span class="sxs-lookup"><span data-stu-id="a56f3-114">To Restore from PowerPivot</span></span>  
  
1.  <span data-ttu-id="a56f3-115">En SSMS, en la instancia de Active Directory en la que se va a realizar la restauración, haga clic con el botón secundario en **Bases de datos**y, a continuación, en **Restaurar desde PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="a56f3-115">In SSMS, in the Active Directory instance you want to restore to, right click **Databases**, and then click **Restore from PowerPivot**.</span></span>  
  
2.  <span data-ttu-id="a56f3-116">En el cuadro de diálogo **Restaurar desde PowerPivot**, en **Origen de restauración**, en **Archivo de copia de seguridad**, haga clic en **Examinar** y seleccione un archivo.abf o.xslx desde el que va a realizar la restauración.</span><span class="sxs-lookup"><span data-stu-id="a56f3-116">In the **Restore from PowerPivot** dialog box, in **Restore Source**, in **Backup file**, click **Browse**, and then select an .abf or .xslx file to restore from.</span></span>  
  
3.  <span data-ttu-id="a56f3-117">En **Restaurar destino**, en **Restaurar base de datos**, escriba un nombre para una base de datos nueva o para una base de datos existente.</span><span class="sxs-lookup"><span data-stu-id="a56f3-117">In **Restore Target**, in **Restore database**, type a name for a new database or for an existing database.</span></span> <span data-ttu-id="a56f3-118">Si no especifica ningún nombre, se usa el nombre del libro.</span><span class="sxs-lookup"><span data-stu-id="a56f3-118">If you do not specify a name, the name of the workbook is used.</span></span>  
  
4.  <span data-ttu-id="a56f3-119">En **Ubicación de almacenamiento**, haga clic en **Examinar** y seleccione una ubicación para almacenar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a56f3-119">In **Storage location**, click **Browse**, and then select a location to store the database.</span></span>  
  
5.  <span data-ttu-id="a56f3-120">En **Opciones**, deje activada **Incluir información de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="a56f3-120">In **Options**, leave **Include security information** checked.</span></span> <span data-ttu-id="a56f3-121">Al restaurar desde un libro PowerPivot, este valor no se aplica.</span><span class="sxs-lookup"><span data-stu-id="a56f3-121">When restoring from a PowerPivot workbook, this setting does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a56f3-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a56f3-122">See Also</span></span>  
 <span data-ttu-id="a56f3-123">[Bases de datos de modelo tabular &#40;SSAS tabular&#41;](tabular-model-databases-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="a56f3-123">[Tabular Model Databases &#40;SSAS Tabular&#41;](tabular-model-databases-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="a56f3-124">Importar desde PowerPivot &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="a56f3-124">Import from PowerPivot &#40;SSAS Tabular&#41;</span></span>](import-from-power-pivot-ssas-tabular.md)  
  
  
