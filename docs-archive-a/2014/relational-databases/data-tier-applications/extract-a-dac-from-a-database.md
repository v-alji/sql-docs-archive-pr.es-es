---
title: Extraer una DAC de una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.extractdacwizard.buildandsave.f1
- sql12.swb.extractdacwizard.setdacproperties.f1
- sql12.swb.extractdacwizard.validationandsummary.f1
- sql12.swb.extractdacwizard.introduction.f1
- sql12.swb.extractdacwizard.selectdatapage.f1
helpviewer_keywords:
- extract DAC
- How to [DAC], extract
- data-tier application [SQL Server], extract
- wizard [DAC], extract
ms.assetid: ae52a723-91c4-43fd-bcc7-f8de1d1f90e5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bd024af9c201563773e20bae7e5fded1985abbe1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677162"
---
# <a name="extract-a-dac-from-a-database"></a><span data-ttu-id="c1ecc-102">Extraer una DAC de una base de datos</span><span class="sxs-lookup"><span data-stu-id="c1ecc-102">Extract a DAC From a Database</span></span>
  <span data-ttu-id="c1ecc-103">Use el **Asistente para extraer aplicación de capa de datos** o un script de Windows PowerShell para extraer un paquete de aplicación de capa de datos (DAC) de una base de datos de SQL Server existente.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-103">Use either the **Extract Data-tier Application Wizard** or a Windows PowerShell script to extract a data-tier application (DAC) package from an existing SQL Server database.</span></span> <span data-ttu-id="c1ecc-104">El proceso de extracción crea un archivo de paquete DAC que contiene definiciones de los objetos de base de datos y sus elementos relacionados a nivel de instancia.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-104">The extraction process creates a DAC package file that contains definitions of the database objects and their related instance-level elements.</span></span> <span data-ttu-id="c1ecc-105">Por ejemplo, un archivo de paquete DAC contiene las tablas de base de datos, procedimientos almacenados, vistas y usuarios, junto con los inicios de sesión que se asignan a los usuarios de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-105">For example, a DAC package file contains the database tables, stored procedures, views, and users, along with the logins that map to the database users.</span></span>  
  
-   <span data-ttu-id="c1ecc-106">**Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions), [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-106">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="c1ecc-107">**Para extraer una DAC, mediante:**  [El Asistente Extraer aplicación de capa de datos](#UsingDACExtractWizard), [PowerShell](#ExtractDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-107">**To extract a DAC, using:**  [The Extract Data-tier Application Wizard](#UsingDACExtractWizard), [PowerShell](#ExtractDACPowerShell)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="c1ecc-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="c1ecc-108">Before You Begin</span></span>  
 <span data-ttu-id="c1ecc-109">Puede extraer una DAC de las bases de datos que residen en instancias de [!INCLUDE[ssSDS](../../includes/sssds-md.md)]o [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] Service Pack 4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-109">You can extract a DAC from databases residing on instances of [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] Service Pack 4 or later.</span></span> <span data-ttu-id="c1ecc-110">Si el proceso de extracción se ejecuta en una base de datos que se implementó a partir de una DAC, solo las definiciones de los objetos de la base de datos se extraen.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-110">If the extraction process is run against a database that was deployed from a DAC, only the definitions of the objects in the database are extracted.</span></span> <span data-ttu-id="c1ecc-111">El proceso no hace referencia a la DAC registrada en `msdb` (**maestra** en [!INCLUDE[ssSDS](../../includes/sssds-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="c1ecc-111">The process does not reference the DAC registered in `msdb` (**master** in [!INCLUDE[ssSDS](../../includes/sssds-md.md)]).</span></span> <span data-ttu-id="c1ecc-112">El proceso de extracción no registra la definición de DAC en la instancia actual del motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-112">The extraction process does not register the DAC definition in the current instance of the Database Engine.</span></span> <span data-ttu-id="c1ecc-113">Para obtener más información sobre el registro de una DAC, vea [Register a Database As a DAC](register-a-database-as-a-dac.md).</span><span class="sxs-lookup"><span data-stu-id="c1ecc-113">For more information about registering a DAC, see [Register a Database As a DAC](register-a-database-as-a-dac.md).</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="c1ecc-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="c1ecc-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="c1ecc-115">Una DAC se puede extraer solo de una base de datos de [!INCLUDE[ssSDS](../../includes/sssds-md.md)]o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) o posterior.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-115">A DAC can only be extracted from a database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span> <span data-ttu-id="c1ecc-116">No puede extraer ninguna DAC si la base de datos tiene objetos que no se admiten en una DAC o usuarios contenidos.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-116">You cannot extract a DAC if the database has objects that are not supported in a DAC, or contained users.</span></span> <span data-ttu-id="c1ecc-117">Para obtener más información acerca de los objetos admitidos por una DAC, vea [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span><span class="sxs-lookup"><span data-stu-id="c1ecc-117">For more information about the types of objects supported in a DAC, see [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c1ecc-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="c1ecc-118">Permissions</span></span>  
 <span data-ttu-id="c1ecc-119">La extracción de una DAC requiere al menos permisos ALTER ANY LOGIN y VIEW DEFINITION en el ámbito de la base de datos, así como permisos SELECT en **sys.sql_expression_dependencies**.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-119">Extracting a DAC requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, as well as SELECT permissions on **sys.sql_expression_dependencies**.</span></span> <span data-ttu-id="c1ecc-120">La extracción de una DAC la pueden realizar los miembros del rol fijo de servidor securityadmin que sean también miembros del rol fijo de base de datos database_owner en la base de datos de la que se extrae la DAC.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-120">Extracting a DAC can be done by members of the securityadmin fixed server role who are also members of the database_owner fixed database role in the database from which the DAC is extracted.</span></span> <span data-ttu-id="c1ecc-121">Los miembros del rol fijo de servidor sysadmin o de la cuenta de administrador del sistema de SQL Server integrada denominada **sa** también pueden extraer una DAC.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-121">Members of the sysadmin fixed server role or the built-in SQL Server system administrator account named **sa** can also extract a DAC.</span></span>  
  
##  <a name="using-the-extract-data-tier-application-wizard"></a><a name="UsingDACExtractWizard"></a> <span data-ttu-id="c1ecc-122">Usar el Asistente de Extraer aplicación de capa de datos</span><span class="sxs-lookup"><span data-stu-id="c1ecc-122">Using the Extract Data-tier Application Wizard</span></span>  
 <span data-ttu-id="c1ecc-123">**Para extraer una DAC mediante un asistente**</span><span class="sxs-lookup"><span data-stu-id="c1ecc-123">**To Extract a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="c1ecc-124">En **Explorador de objetos**, expanda el nodo de la instancia que contiene la base de datos de la que debe extraerse la DAC.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-124">In **Object Explorer**, expand the node for the instance containing the database from which the DAC is to be extracted.</span></span>  
  
2.  <span data-ttu-id="c1ecc-125">Expanda el nodo **Bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="c1ecc-125">Expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="c1ecc-126">Haga clic con el botón derecho en el nodo de la base de datos del que se va a extraer la DAC, haga clic en **Tareas** y, después, seleccione **Extraer aplicación de capa de datos...**.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-126">Right-click the node for the database from which the DAC is to be extracted, point to **Tasks**, and then select **Extract Data-tier Application...**</span></span>  
  
4.  <span data-ttu-id="c1ecc-127">Complete los cuadros de diálogo del asistente:</span><span class="sxs-lookup"><span data-stu-id="c1ecc-127">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="c1ecc-128">Página Introducción</span><span class="sxs-lookup"><span data-stu-id="c1ecc-128">Introduction Page</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="c1ecc-129">Seleccione Página de datos</span><span class="sxs-lookup"><span data-stu-id="c1ecc-129">Select Data Page</span></span>](#SelectData)  
  
    3.  [<span data-ttu-id="c1ecc-130">Página Definir propiedades</span><span class="sxs-lookup"><span data-stu-id="c1ecc-130">Set Properties Page</span></span>](#SetProperties)  
  
    4.  [<span data-ttu-id="c1ecc-131">Página Validación y resumen</span><span class="sxs-lookup"><span data-stu-id="c1ecc-131">Validation and Summary Page</span></span>](#ValidateSummary)  
  
    5.  [<span data-ttu-id="c1ecc-132">Página Compilar paquete</span><span class="sxs-lookup"><span data-stu-id="c1ecc-132">Build Package Page</span></span>](#BuildPackage)  
  
###  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="c1ecc-133">Página Introducción</span><span class="sxs-lookup"><span data-stu-id="c1ecc-133">Introduction Page</span></span>  
 <span data-ttu-id="c1ecc-134">Esta página describe los pasos para extraer una aplicación de capa de datos.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-134">This page describes the steps for extracting a data-tier application.</span></span>  
  
 <span data-ttu-id="c1ecc-135">**No volver a mostrar esta página.**</span><span class="sxs-lookup"><span data-stu-id="c1ecc-135">**Do not show this page again.**</span></span> <span data-ttu-id="c1ecc-136">- Haga clic en la casilla para evitar que la página se muestre en el futuro.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-136">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="c1ecc-137">**Siguiente >**: continúa hasta la página **Elegir método**.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-137">**Next >** - Proceeds to the **Choose Method** page.</span></span>  
  
 <span data-ttu-id="c1ecc-138">**Cancelar:** termina el asistente sin extraer una aplicación de capa de datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-138">**Cancel** - Ends the wizard without extracting a data-tier application from the database.</span></span>  
  
###  <a name="select-data-page"></a><a name="SelectData"></a><span data-ttu-id="c1ecc-139">Página seleccionar datos</span><span class="sxs-lookup"><span data-stu-id="c1ecc-139">Select Data Page</span></span>  
 <span data-ttu-id="c1ecc-140">Use esta página del asistente para seleccionar los datos de referencia que desee incluir en el archivo de paquete de la aplicación de capa de datos (DAC).</span><span class="sxs-lookup"><span data-stu-id="c1ecc-140">Use this page of the wizard to select the reference data that you want to include in your data-tier application (DAC) package file.</span></span> <span data-ttu-id="c1ecc-141">La inclusión de datos en el paquete DAC es opcional.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-141">Including data in your DAC package is optional.</span></span> <span data-ttu-id="c1ecc-142">El paquete DAC ya incluirá el esquema de todos los objetos de base de datos compatibles y los objetos de instancia relacionados con la base de datos</span><span class="sxs-lookup"><span data-stu-id="c1ecc-142">The DAC package will already include the schema of all supported database objects and instance objects related to your database.</span></span>  
  
 <span data-ttu-id="c1ecc-143">Puede incluir hasta 10 MB de datos de referencia en el archivo del paquete DAC.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-143">You can include up to 10 MB of reference data in your DAC package file.</span></span> <span data-ttu-id="c1ecc-144">Pero, en cuanto a las tablas que se van a incluir en el DAC, puede que no contengan tipos de datos de objetos binarios grandes (BLOB) como **image** o **varchar(max)**.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-144">However, for tables to be included in the DAC, they may not contain binary large object (BLOB) data types such as **image** or **varchar(max)**.</span></span> <span data-ttu-id="c1ecc-145">Para extraer cantidades de datos más grandes con el fin de transferirlos a otra base de datos, use SQL Server Integration Services, la utilidad de copia masiva o una de las muchas otras técnicas de migración de datos.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-145">To extract larger amounts of data for transferring to another database, use SQL Server Integration Services, the bulk copy utility, or one of many other data migration techniques.</span></span>  
  
 <span data-ttu-id="c1ecc-146">**Tabla de base de datos:** active la casilla situada junto a las tablas de base de datos que contengan los datos que quiera incluir en el paquete DAC.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-146">**Database table** - Select the check box next to the database tables which contain the data that you want to include in your DAC package.</span></span> <span data-ttu-id="c1ecc-147">Puede seleccionar hasta diez tablas con 10.000 filas o menos.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-147">You can select up to ten tables that have 10,000 rows or less.</span></span>  
  
###  <a name="set-properties-page"></a><a name="SetProperties"></a> <span data-ttu-id="c1ecc-148">Página Definir propiedades</span><span class="sxs-lookup"><span data-stu-id="c1ecc-148">Set Properties Page</span></span>  
 <span data-ttu-id="c1ecc-149">Use esta página del asistente para describir la aplicación de capa de datos (DAC).</span><span class="sxs-lookup"><span data-stu-id="c1ecc-149">Use this page of the wizard to describe the data-tier application (DAC).</span></span> <span data-ttu-id="c1ecc-150">Estas propiedades se usan para identificar la DAC y contribuyen a diferenciarla de otras.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-150">These properties are used to identify the DAC and help distinguish it from others.</span></span>  
  
 <span data-ttu-id="c1ecc-151">**Nombre:** este nombre identifica la DAC.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-151">**Name** - This name identifies the DAC.</span></span> <span data-ttu-id="c1ecc-152">Puede ser distinto del nombre del archivo de paquete DAC y debe describir la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-152">It can be different than the name of the DAC package file and should describe your application.</span></span> <span data-ttu-id="c1ecc-153">Por ejemplo, si la base de datos se usa para una aplicación de finanzas, puede llamar Finanza a la DAC.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-153">For example, if the database is used for a finance application, you may wish to name the DAC Finance.</span></span>  
  
 <span data-ttu-id="c1ecc-154">**Versión (use xx.xx.xx.xx, donde x es un número):** valor numérico que identifica la versión de la DAC.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-154">**Version (use xx.xx.xx.xx, where x is a number)** - A numeric value that identifies the version of the DAC.</span></span> <span data-ttu-id="c1ecc-155">La versión de DAC se usa en Visual Studio para identificar la versión de la DAC en la que están trabajando los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-155">The DAC version is used in Visual Studio to identify the version of the DAC that developers are working on.</span></span> <span data-ttu-id="c1ecc-156">Al implementar una DAC, la versión se almacena en la `msdb` base de datos y se puede ver después en el nodo **aplicaciones de capa de datos** en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c1ecc-156">When deploying a DAC, the version is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c1ecc-157">**Descripción:** opcional.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-157">**Description:** - Optional.</span></span> <span data-ttu-id="c1ecc-158">Describe la DAC.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-158">Describes the DAC.</span></span> <span data-ttu-id="c1ecc-159">Al implementar una DAC, la descripción se almacena en la `msdb` base de datos y se puede ver después en el nodo **aplicaciones de capa de datos** en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c1ecc-159">When deploying a DAC, the description is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="c1ecc-160">**Guardar en archivo de paquete DAC (incluye extensión .dacpac con nombre de archivo):** guarda la DAC en un archivo de paquete DAC, con una extensión .dacpac.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-160">**Save to DAC package file (include .dacpac extension with file name):** - Saves the DAC to a DAC package file, with a .dacpac extension.</span></span> <span data-ttu-id="c1ecc-161">Haga clic en el botón **Examinar** para especificar el nombre y la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-161">Click the **Browse** button to specify a name and location for the file.</span></span>  
  
 <span data-ttu-id="c1ecc-162">**Sobrescribir el archivo existente:** active esta casilla para reemplazar el archivo de paquete DAC si ya existe uno con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-162">**Overwrite existing file** - Select this check box to replace the DAC package file if one already exists with the same name.</span></span>  
  
###  <a name="validation-and-summary-page"></a><a name="ValidateSummary"></a> <span data-ttu-id="c1ecc-163">Página Validación y resumen</span><span class="sxs-lookup"><span data-stu-id="c1ecc-163">Validation and Summary Page</span></span>  
 <span data-ttu-id="c1ecc-164">En esta página, el asistente valida que una aplicación de capa de datos (DAC) admite todos los objetos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-164">On this page, the wizard validates that all database objects are supported by a data-tier application (DAC).</span></span> <span data-ttu-id="c1ecc-165">También comprueba las dependencias entre los objetos de base de datos para determinar el conjunto de objetos que se pueden incluir correctamente en la DAC.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-165">It also checks dependencies across database objects to determine the set of objects that can be successfully included in the DAC.</span></span> <span data-ttu-id="c1ecc-166">Tras ello, muestra el informe de validación y resume las opciones que ha seleccionado en este asistente.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-166">After that, it displays the validation report and summarizes the options that you have selected in this wizard.</span></span> <span data-ttu-id="c1ecc-167">Para cambiar una opción, haga clic en **Anterior**.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-167">To change an option, click **Previous**.</span></span> <span data-ttu-id="c1ecc-168">Para empezar a extraer una DAC, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-168">To begin extracting a DAC, click **Next**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1ecc-169">Si una DAC no admite uno o varios objetos, el botón **Siguiente** está deshabilitado y el proceso de extracción puede no continuar.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-169">If one or more objects are not supported by a DAC, then the **Next** button is disabled and the extraction process may not continue.</span></span> <span data-ttu-id="c1ecc-170">En estos casos, se recomienda quitar los objetos no admitidos y volver a ejecutar este asistente.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-170">In such cases, it is recommended to remove the non-supported objects and then run this wizard again.</span></span>  
  
 <span data-ttu-id="c1ecc-171">**Resumen:** un resumen de las opciones que ha seleccionado aparecen en **Propiedades de DAC**.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-171">**Summary** - A summary of the options you have selected are listed under **DAC properties**.</span></span> <span data-ttu-id="c1ecc-172">Los resultados de la validación se enumeran en **Objetos de DAC**.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-172">The results of the validation are listed under **DAC objects**.</span></span> <span data-ttu-id="c1ecc-173">La validación produce tres tipos de resultados:</span><span class="sxs-lookup"><span data-stu-id="c1ecc-173">There are three types of results from the validation:</span></span>  
  
-   <span data-ttu-id="c1ecc-174">**Objetos admitidos en una DAC**: se admiten estos objetos y sus dependencias y se pueden incluir correctamente en la DAC.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-174">**Objects included in DAC successfully**: these objects and their dependencies are supported, and can be included in the DAC successfully.</span></span>  
  
-   <span data-ttu-id="c1ecc-175">**Objetos admitidos en una DAC con advertencias**: se admiten estos objetos, pero dependen de otros objetos que no se admiten en una DAC.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-175">**Objects included in DAC with warnings**: these objects are supported, but depend on other objects that are not supported in a DAC.</span></span>  
  
-   <span data-ttu-id="c1ecc-176">**Objetos no admitidos en una DAC**: estos objetos no se admiten y se deben quitar de la base de datos antes de extraer una DAC correctamente.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-176">**Objects not included in DAC**: these objects are not supported and must be removed from the database before successfully extracting a DAC.</span></span>  
  
 <span data-ttu-id="c1ecc-177">El proceso de validación comprueba varios niveles de dependencias.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-177">The validation process checks multiple levels of dependencies.</span></span> <span data-ttu-id="c1ecc-178">Por ejemplo, si un procedimiento almacenado depende de una tabla que usa un tipo de datos CLR no admitido, el procedimiento almacenado se enumerará en **Objetos incluidos en DAC con advertencias**.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-178">For example, if a stored procedure depends on a table that uses the unsupported CLR data type, the stored procedure will be listed under **Objects included in DAC with warnings**.</span></span>  
  
 <span data-ttu-id="c1ecc-179">Si una DAC no admite uno o varios objetos, el botón **Siguiente** está deshabilitado y el proceso de extracción no continuará.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-179">If one or more objects are not supported by a DAC, then the **Next** button is disabled and the extraction process will not continue.</span></span> <span data-ttu-id="c1ecc-180">En estos casos, se recomienda quitar los objetos que no están admitidos y volver a ejecutar este asistente.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-180">In such cases, it is recommended to remove the objects that are not supported and then run this wizard again.</span></span>  
  
 <span data-ttu-id="c1ecc-181">**Guardar informe:** permite guardar un archivo basado en HTML que enumera todos los objetos del nodo **Objetos DAC** en el resumen.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-181">**Save Report** - Enables you to save an HTML-based file that lists all of the objects under the **DAC Objects** node in the summary.</span></span> <span data-ttu-id="c1ecc-182">Este informe puede ser útil cuando algunos de objetos de base de datos no se admiten en una DAC.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-182">This report can be useful when some of your database objects are not supported in a DAC.</span></span> <span data-ttu-id="c1ecc-183">Use el informe para cambiar o quitar objetos que no se admiten, antes de intentar extraer la DAC de nuevo.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-183">Use the report to change or remove objects that are not supported, before trying to extract the DAC again.</span></span>  
  
###  <a name="build-package-page"></a><a name="BuildPackage"></a><span data-ttu-id="c1ecc-184">Página compilar paquete</span><span class="sxs-lookup"><span data-stu-id="c1ecc-184">Build Package Page</span></span>  
 <span data-ttu-id="c1ecc-185">Use esta página para supervisar el progreso del asistente cuando extrae la aplicación de capa de datos (DAC).</span><span class="sxs-lookup"><span data-stu-id="c1ecc-185">Use this page to monitor the progress of the wizard as it extracts the data-tier application (DAC).</span></span>  
  
 <span data-ttu-id="c1ecc-186">**Acción:** durante la acción **Crear y guardar archivo de paquete DAC** , el asistente extrae una DAC de la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-186">**Action** - During the **Create and save DAC package file** action, the wizard extracts a DAC from your SQL Server database.</span></span> <span data-ttu-id="c1ecc-187">A continuación, se crea un paquete DAC en memoria y se guarda en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-187">Then, a DAC package is created in memory and saved to the location you specified.</span></span> <span data-ttu-id="c1ecc-188">Haga clic en los vínculos de la columna **Resultado** para ver el resultado del paso correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-188">Click on the links in the **Result** column to see the outcome of the corresponding step.</span></span>  
  
 <span data-ttu-id="c1ecc-189">**Guardar informe:** haga clic en esta opción para guardar los resultados del progreso del asistente en un archivo.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-189">**Save Report** - Click to save the results of the wizard's progress to a file.</span></span>  
  
 <span data-ttu-id="c1ecc-190">**Terminar** : haga clic en esta opción para cerrar el asistente después de que se haya completado el procesamiento o si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-190">**Finish** - Click to close the wizard after processing has completed, or if an error occurs.</span></span>  
  
##  <a name="extract-a-dac-using-powershell"></a><a name="ExtractDACPowerShell"></a><span data-ttu-id="c1ecc-191">Extracción de una DAC mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1ecc-191">Extract a DAC Using PowerShell</span></span>  
 <span data-ttu-id="c1ecc-192">**Para extraer una DAC de una base de datos con el método Extract() en un script de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c1ecc-192">**To extract a DAC from a database using the Extract() method in a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="c1ecc-193">Cree un objeto SMO Server y establézcalo en la instancia que contiene la base de datos desde la que se va a extraer una DAC.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-193">Create a SMO Server object and set it to the instance that contains the database from which the DAC is to be extracted.</span></span>  
  
2.  <span data-ttu-id="c1ecc-194">Agregue una variable que especifique el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-194">Add a variable that specifies the name of the database.</span></span>  
  
3.  <span data-ttu-id="c1ecc-195">Especifique los metadatos de la DAC, como su nombre, versión y descripción.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-195">Specify the metadata for the DAC, such as the DAC name, version, and description.</span></span>  
  
4.  <span data-ttu-id="c1ecc-196">Especifique la ruta de acceso y el nombre de archivo para el archivo de paquete DAC extraído.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-196">Specify the path and file name for the extracted DAC package file.</span></span>  
  
5.  <span data-ttu-id="c1ecc-197">Ejecutar el método Extract con la información especificada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-197">Run the Extract method with the information specified above.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="c1ecc-198">Ejemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-198">Example (PowerShell)</span></span>  
 <span data-ttu-id="c1ecc-199">En el siguiente ejemplo se extrae una DAC denominada MyApplication de una base de datos llamada MyDB.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-199">The following example extracts a DAC named MyApplication from a database named MyDB.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Specify the database to extract to a DAC.  
$dbname = "MyDB"  
  
## Specify the DAC metadata.  
$applicationname = "MyApplication"  
$version = "1.0.0.0"  
$description = "This DAC defines the database used by my application."  
  
## Specify the location and name for the extracted DAC package.  
$dacpacPath = "C:\MyDACs\MyApplication.dacpac"  
  
## Extract the DAC.  
$extractionunit = New-Object Microsoft.SqlServer.Management.Dac.DacExtractionUnit($srv, $dbname, $applicationname, $version)  
$extractionunit.Description = $description  
$extractionunit.Extract($dacpacPath)  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1ecc-200">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1ecc-200">See Also</span></span>  
 [<span data-ttu-id="c1ecc-201">Aplicaciones de capa de datos</span><span class="sxs-lookup"><span data-stu-id="c1ecc-201">Data-tier Applications</span></span>](data-tier-applications.md)  
