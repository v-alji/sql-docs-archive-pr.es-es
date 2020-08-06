---
title: Eliminación de una aplicación de capa de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.deletedacwizard.introduction.f1
- sql12.swb.deletedacwizard.deletedac.f1
- sql12.swb.deletedacwizard.summary.f1
- sql12.swb.deletedacwizard.choosemethod.f1
helpviewer_keywords:
- How to [DAC], delete
- data-tier application [SQL Server], delete
- wizard [DAC], delete
- delete DAC
ms.assetid: 16fe1c18-4486-424d-81d6-d276ed97482f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 602256c287a8c7bcf9d3fa5597b2fec2085c626c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748126"
---
# <a name="delete-a-data-tier-application"></a><span data-ttu-id="c6896-102">Eliminar una aplicación de capa de datos</span><span class="sxs-lookup"><span data-stu-id="c6896-102">Delete a Data-tier Application</span></span>
  <span data-ttu-id="c6896-103">Puede eliminar una aplicación de capa de datos mediante el Asistente para eliminar aplicación de capa de datos o un script de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6896-103">You can delete a data-tier application by using either the Delete Data-tier Application wizard or a Windows PowerShell script.</span></span> <span data-ttu-id="c6896-104">Puede especificar si la base de datos asociada se conserva, se separa o se quita.</span><span class="sxs-lookup"><span data-stu-id="c6896-104">You can specify whether the associated database is retained, detached, or dropped.</span></span>  
  
-   <span data-ttu-id="c6896-105">**Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions), [Permisos](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="c6896-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="c6896-106">**Para actualizar una DAC mediante:**  [el Asistente para registrar aplicación de capa de datos](#UsingDeleteDACWizard), [PowerShell](#DeleteDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="c6896-106">**To upgrade a DAC, using:**  [The Register Data-tier Application Wizard](#UsingDeleteDACWizard), [PowerShell](#DeleteDACPowerShell)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="c6896-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="c6896-107">Before You Begin</span></span>  
 <span data-ttu-id="c6896-108">Cuando elimine una instancia de la aplicación de capa de datos (DAC), elija una de tres opciones que especifican lo que se va a hacer con la base de datos asociada a la aplicación de capa de datos.</span><span class="sxs-lookup"><span data-stu-id="c6896-108">When you delete a data-tier application (DAC) instance, you choose one of three options specifying what is to be done with the database associated with the data-tier application.</span></span> <span data-ttu-id="c6896-109">Las tres opciones eliminan los metadatos de la definición de DAC.</span><span class="sxs-lookup"><span data-stu-id="c6896-109">All three options delete the DAC definition metadata.</span></span> <span data-ttu-id="c6896-110">Las opciones difieren en lo que hacen con la base de datos asociada a la aplicación de capa de datos.</span><span class="sxs-lookup"><span data-stu-id="c6896-110">The options differ in what they do with the database associated with the data-tier application.</span></span> <span data-ttu-id="c6896-111">El asistente no elimina ninguno de los objetos del nivel de instancia asociado a la DAC o la base de datos, como los inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="c6896-111">The wizard does not delete any of the instance-level objects associated with the DAC or database, such as logins.</span></span>  
  
|<span data-ttu-id="c6896-112">Opción</span><span class="sxs-lookup"><span data-stu-id="c6896-112">Option</span></span>|<span data-ttu-id="c6896-113">Acciones de base de datos</span><span class="sxs-lookup"><span data-stu-id="c6896-113">Database actions</span></span>|  
|------------|----------------------|  
|<span data-ttu-id="c6896-114">Eliminar registro</span><span class="sxs-lookup"><span data-stu-id="c6896-114">Delete registration</span></span>|<span data-ttu-id="c6896-115">La base de datos asociada permanece intacta.</span><span class="sxs-lookup"><span data-stu-id="c6896-115">The associated database remains intact.</span></span>|  
|<span data-ttu-id="c6896-116">Separar base de datos</span><span class="sxs-lookup"><span data-stu-id="c6896-116">Detach database</span></span>|<span data-ttu-id="c6896-117">La base de datos asociada se separa.</span><span class="sxs-lookup"><span data-stu-id="c6896-117">The associated database is detached.</span></span> <span data-ttu-id="c6896-118">La instancia del motor de base de datos no puede hacer referencia a la base de datos, pero los archivos de registro y de datos están intactos.</span><span class="sxs-lookup"><span data-stu-id="c6896-118">The instance of the Database Engine cannot reference the database, but the data and log files are intact.</span></span>|  
|<span data-ttu-id="c6896-119">Eliminar base de datos</span><span class="sxs-lookup"><span data-stu-id="c6896-119">Delete database</span></span>|<span data-ttu-id="c6896-120">Se quita la base de datos asociada.</span><span class="sxs-lookup"><span data-stu-id="c6896-120">The associated database is dropped.</span></span> <span data-ttu-id="c6896-121">Se eliminan los archivos de registro y datos.</span><span class="sxs-lookup"><span data-stu-id="c6896-121">The data and log files are deleted.</span></span>|  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="c6896-122">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="c6896-122">Limitations and Restrictions</span></span>  
 <span data-ttu-id="c6896-123">No hay ningún mecanismo automático para restaurar los metadatos o la base de datos de una DAC si esta se elimina.</span><span class="sxs-lookup"><span data-stu-id="c6896-123">There is no automatic mechanism to restore the DAC definition metadata or the database after you delete a DAC.</span></span> <span data-ttu-id="c6896-124">La forma de volver a generar manualmente la instancia de la DAC depende de la opción de eliminación.</span><span class="sxs-lookup"><span data-stu-id="c6896-124">How you can manually rebuild the DAC instance depends on the delete option.</span></span>  
  
|<span data-ttu-id="c6896-125">Opción</span><span class="sxs-lookup"><span data-stu-id="c6896-125">Option</span></span>|<span data-ttu-id="c6896-126">Volver a generar la instancia de DAC</span><span class="sxs-lookup"><span data-stu-id="c6896-126">How to Rebuild the DAC Instance</span></span>|  
|------------|-------------------------------------|  
|<span data-ttu-id="c6896-127">Eliminar registro</span><span class="sxs-lookup"><span data-stu-id="c6896-127">Delete registration</span></span>|<span data-ttu-id="c6896-128">Registre una DAC desde la base de datos que se ha mantenida en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c6896-128">Register a DAC from the database left in place.</span></span>|  
|<span data-ttu-id="c6896-129">Separar base de datos</span><span class="sxs-lookup"><span data-stu-id="c6896-129">Detach database</span></span>|<span data-ttu-id="c6896-130">Vuelva a adjuntar la base de datos usando **sp_attachdb** o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]y después registre una nueva instancia de DAC desde la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c6896-130">Re-attach the database by using **sp_attachdb** or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then register a new DAC instance from the database.</span></span>|  
|<span data-ttu-id="c6896-131">Eliminar base de datos</span><span class="sxs-lookup"><span data-stu-id="c6896-131">Delete database</span></span>|<span data-ttu-id="c6896-132">Restaure la base de datos a partir de una copia de seguridad completa realizada antes de que se eliminara la DAC, y, a continuación, registre una nueva instancia de la DAC a partir de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c6896-132">Restore the database from a full backup made before the DAC was deleted, and then register a new DAC instance from the database.</span></span>|  
  
> [!WARNING]  
>  <span data-ttu-id="c6896-133">Recompilar una instancia de la DAC mediante el registro de una DAC desde una base de datos restaurada o adjuntada no volverá a crear algunas partes de la DAC original, como la directiva de selección de servidor.</span><span class="sxs-lookup"><span data-stu-id="c6896-133">Rebuilding a DAC instance by registering a DAC from a restored or re-attached database will not recreate some parts of the original DAC, such as the server selection policy.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c6896-134">Permisos</span><span class="sxs-lookup"><span data-stu-id="c6896-134">Permissions</span></span>  
 <span data-ttu-id="c6896-135">Solo los miembros de los roles fijos de servidor **sysadmin** o **serveradmin** , o el propietario de la base de datos, pueden eliminar una DAC.</span><span class="sxs-lookup"><span data-stu-id="c6896-135">A DAC can only be deleted by members of the **sysadmin** or **serveradmin** fixed server roles, or by the database owner.</span></span> <span data-ttu-id="c6896-136">La cuenta de administrador del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integrada denominada **sa** también puede iniciar el asistente.</span><span class="sxs-lookup"><span data-stu-id="c6896-136">The built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator account named **sa** can also launch the wizard.</span></span>  
  
##  <a name="using-the-delete-data-tier-application-wizard"></a><a name="UsingDeleteDACWizard"></a> <span data-ttu-id="c6896-137">Usar el asistente Eliminar aplicación de capa de datos</span><span class="sxs-lookup"><span data-stu-id="c6896-137">Using the Delete Data-tier Application Wizard</span></span>  
 <span data-ttu-id="c6896-138">**Para eliminar una DAC mediante un asistente**</span><span class="sxs-lookup"><span data-stu-id="c6896-138">**To Delete a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="c6896-139">En **Explorador de objetos**, expanda el nodo de la instancia que contiene la DAC que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="c6896-139">In **Object Explorer**, expand the node for the instance containing the DAC to be deleted.</span></span>  
  
2.  <span data-ttu-id="c6896-140">Expanda el nodo **Administración** .</span><span class="sxs-lookup"><span data-stu-id="c6896-140">Expand the **Management** node.</span></span>  
  
3.  <span data-ttu-id="c6896-141">Expanda el nodo **Aplicaciones de capa de datos** .</span><span class="sxs-lookup"><span data-stu-id="c6896-141">Expand the **Data-tier Applications** node.</span></span>  
  
4.  <span data-ttu-id="c6896-142">Haga clic con el botón derecho en la DAC que quiere eliminar y luego seleccione **Eliminar aplicación de capa de datos...** .</span><span class="sxs-lookup"><span data-stu-id="c6896-142">Right-click the DAC to be deleted, and then select **Delete Data-tier Application...**</span></span>  
  
5.  <span data-ttu-id="c6896-143">Complete los cuadros de diálogo del asistente:</span><span class="sxs-lookup"><span data-stu-id="c6896-143">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="c6896-144">Introducción</span><span class="sxs-lookup"><span data-stu-id="c6896-144">Introduction</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="c6896-145">Elegir método</span><span class="sxs-lookup"><span data-stu-id="c6896-145">Choose Method</span></span>](#Choose_method)  
  
    3.  [<span data-ttu-id="c6896-146">Resumen</span><span class="sxs-lookup"><span data-stu-id="c6896-146">Summary</span></span>](#Summary)  
  
    4.  [<span data-ttu-id="c6896-147">Eliminar aplicación de capa de datos</span><span class="sxs-lookup"><span data-stu-id="c6896-147">Delete Data-tier Application</span></span>](#Delete_datatier_application)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="c6896-148">Página Introducción</span><span class="sxs-lookup"><span data-stu-id="c6896-148">Introduction Page</span></span>  
 <span data-ttu-id="c6896-149">Esta página describe los pasos para eliminar una aplicación de capa de datos.</span><span class="sxs-lookup"><span data-stu-id="c6896-149">This page describes the steps for deleting a data-tier application.</span></span>  
  
 <span data-ttu-id="c6896-150">**No volver a mostrar esta página.**</span><span class="sxs-lookup"><span data-stu-id="c6896-150">**Do not show this page again.**</span></span> <span data-ttu-id="c6896-151">- Haga clic en la casilla para evitar que la página se muestre en el futuro.</span><span class="sxs-lookup"><span data-stu-id="c6896-151">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="c6896-152">**Siguiente >** : continúa hasta la página **Elegir método**.</span><span class="sxs-lookup"><span data-stu-id="c6896-152">**Next >** - Proceeds to the **Choose Method** page.</span></span>  
  
 <span data-ttu-id="c6896-153">**Cancelar** : termina el asistente sin eliminar una aplicación de capa de datos o base de datos.</span><span class="sxs-lookup"><span data-stu-id="c6896-153">**Cancel** - Ends the wizard without deleting a data-tier application or database.</span></span>  
  
##  <a name="choose-method-page"></a><a name="Choose_method"></a><span data-ttu-id="c6896-154">Página elegir método</span><span class="sxs-lookup"><span data-stu-id="c6896-154">Choose Method Page</span></span>  
 <span data-ttu-id="c6896-155">Use esta página para especificar la opción a fin de controlar la base de datos asociada a la DAC que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="c6896-155">Use this page to specify the option for handling the database associated with the DAC to be deleted.</span></span>  
  
 <span data-ttu-id="c6896-156">**Eliminar registro** : quita los metadatos que definen la aplicación de capa de datos, pero deja intacta la base de datos asociada.</span><span class="sxs-lookup"><span data-stu-id="c6896-156">**Delete registration** - Removes the metadata defining the data-tier application, but leaves the associated database intact.</span></span>  
  
 <span data-ttu-id="c6896-157">**Separar base de datos** : quita los metadatos que definen la aplicación de capa de datos y separa la base de datos asociada.</span><span class="sxs-lookup"><span data-stu-id="c6896-157">**Detach database** - Removes the metadata defining the data-tier application and detaches the associated database.</span></span>  
  
 <span data-ttu-id="c6896-158">Esa instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)]no puede hacer referencia ya a la base de datos, pero los archivos de registro y de datos permanecen intactos.</span><span class="sxs-lookup"><span data-stu-id="c6896-158">The database can no longer be referenced by that instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], but the data and log files remain intact.</span></span>  
  
 <span data-ttu-id="c6896-159">**Eliminar base de datos** : quita los metadatos que definen la DAC y quita la base de datos asociada.</span><span class="sxs-lookup"><span data-stu-id="c6896-159">**Delete database** - Removes the metadata defining the DAC and drops the associated database.</span></span>  
  
 <span data-ttu-id="c6896-160">Los archivos de registro y de datos de la base de datos se eliminan de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="c6896-160">The data and log files for the database are permanently deleted.</span></span>  
  
 <span data-ttu-id="c6896-161">\*\* \< Anterior\*\* : vuelve a la página **Introducción** .</span><span class="sxs-lookup"><span data-stu-id="c6896-161">**\< Previous** - Returns to the **Introduction** page.</span></span>  
  
 <span data-ttu-id="c6896-162">**Siguiente >**: avanza a la página **Resumen**.</span><span class="sxs-lookup"><span data-stu-id="c6896-162">**Next >** - Proceeds to the **Summary** page.</span></span>  
  
 <span data-ttu-id="c6896-163">**Cancelar** : termina el asistente sin eliminar la DAC o la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c6896-163">**Cancel** - Ends the wizard without deleting the DAC or database.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="c6896-164">Página Resumen</span><span class="sxs-lookup"><span data-stu-id="c6896-164">Summary Page</span></span>  
 <span data-ttu-id="c6896-165">Use esta página para revisar las acciones que el asistente realizará al eliminar la instancia de la DAC.</span><span class="sxs-lookup"><span data-stu-id="c6896-165">Use this page to review the actions the wizard will take when deleting the DAC instance.</span></span>  
  
 <span data-ttu-id="c6896-166">**Revisar opciones seleccionadas** : revise la DAC, la base de datos y el método de eliminación mostrados en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="c6896-166">**Review your selection summary** - Review the DAC, database, and deletion method displayed in the box.</span></span> <span data-ttu-id="c6896-167">Si la información es correcta, seleccione **Siguiente** o **Finalizar** para eliminar la DAC.</span><span class="sxs-lookup"><span data-stu-id="c6896-167">If the information is correct, select either **Next** or **Finish** to delete the DAC.</span></span> <span data-ttu-id="c6896-168">Si la información de la base de datos y la DAC no es correcta, seleccione **Cancelar** y seleccione la DAC correcta.</span><span class="sxs-lookup"><span data-stu-id="c6896-168">If the DAC and database information is not correct, select **Cancel** and select the correct DAC.</span></span> <span data-ttu-id="c6896-169">Si el método de eliminación no es correcto, seleccione **Anterior** para volver a la página **Elegir método** y seleccione un método diferente.</span><span class="sxs-lookup"><span data-stu-id="c6896-169">If the deletion method is not correct, select **Previous** to return to the **Choose Method** page and select a different method.</span></span>  
  
 <span data-ttu-id="c6896-170">\*\* \< Anterior\*\* : vuelve a la página **elegir método** para elegir otro método de eliminación.</span><span class="sxs-lookup"><span data-stu-id="c6896-170">**\< Previous** - Returns to the **Choose Method** page to choose a different delete method.</span></span>  
  
 <span data-ttu-id="c6896-171">**Siguiente >**: elimina la instancia de DAC mediante el método elegido en la página anterior y avanza a la página **Eliminar aplicación de capa de datos**.</span><span class="sxs-lookup"><span data-stu-id="c6896-171">**Next >** - Deletes the DAC instance using the method you chose on the previous page, and proceeds to the **Delete Data-tier Application** page.</span></span>  
  
 <span data-ttu-id="c6896-172">**Cancelar** : finaliza el asistente sin eliminar la instancia de DAC.</span><span class="sxs-lookup"><span data-stu-id="c6896-172">**Cancel** - Ends the wizard without deleting the DAC instance.</span></span>  
  
##  <a name="delete-data-tier-application-page"></a><a name="Delete_datatier_application"></a><span data-ttu-id="c6896-173">Página eliminar aplicación de capa de datos</span><span class="sxs-lookup"><span data-stu-id="c6896-173">Delete Data-tier Application Page</span></span>  
 <span data-ttu-id="c6896-174">Esta página notifica si la operación de eliminación se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="c6896-174">This page reports the success or failure of the delete operation.</span></span>  
  
 <span data-ttu-id="c6896-175">**Eliminando la DAC** : notifica si cada acción realizada para eliminar la instancia de DAC se ha llevado a cabo correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="c6896-175">**Deleting the DAC** - Reports the success or failure of each action taken to delete the DAC instance.</span></span> <span data-ttu-id="c6896-176">Revise la información para determinar si cada acción se realizó o no correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6896-176">Review the information to determine the success or failure of each action.</span></span> <span data-ttu-id="c6896-177">Cualquier acción que encontrara un error tendrá un vínculo en la columna **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="c6896-177">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="c6896-178">Seleccione el vínculo para ver un informe del error para esa acción.</span><span class="sxs-lookup"><span data-stu-id="c6896-178">Select the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="c6896-179">**Guardar informe** : seleccione este botón para guardar el informe de eliminación en un archivo HTML.</span><span class="sxs-lookup"><span data-stu-id="c6896-179">**Save Report** - Select this button to save the deletion report to an HTML file.</span></span> <span data-ttu-id="c6896-180">El archivo notifica el estado de cada acción, incluidos todos los errores generados por cualquiera de las acciones.</span><span class="sxs-lookup"><span data-stu-id="c6896-180">The file reports the status of each action, including all errors generated by any of the actions.</span></span> <span data-ttu-id="c6896-181">La carpeta predeterminada es una carpeta SQL Server Management Studio\DAC Packages de la carpeta Documentos de su cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="c6896-181">The default folder is a SQL Server Management Studio\DAC Packages folder in the Documents folder of your Windows account..</span></span>  
  
 <span data-ttu-id="c6896-182">**Finalizar** : termina el asistente.</span><span class="sxs-lookup"><span data-stu-id="c6896-182">**Finish** - Ends the wizard.</span></span>  
  
##  <a name="delete-a-dac-using-powershell"></a><a name="DeleteDACPowerShell"></a><span data-ttu-id="c6896-183">Eliminar una DAC mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6896-183">Delete a DAC Using PowerShell</span></span>  
 <span data-ttu-id="c6896-184">**Para eliminar una DAC mediante un script de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c6896-184">**To delete a DAC using a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="c6896-185">Cree un objeto SMO Server y establézcalo en la instancia que contiene la DAC que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="c6896-185">Create a SMO Server object and set it to the instance that contains the DAC to be deleted.</span></span>  
  
2.  <span data-ttu-id="c6896-186">Abra un objeto `ServerConnection` y conéctese a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="c6896-186">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="c6896-187">Use `add_DacActionStarted` y `add_DacActionFinished` para suscribirse a los eventos de actualización de DAC.</span><span class="sxs-lookup"><span data-stu-id="c6896-187">Use `add_DacActionStarted` and `add_DacActionFinished` to subscribe to the DAC upgrade events.</span></span>  
  
4.  <span data-ttu-id="c6896-188">Especifique la DAC que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="c6896-188">Specify the DAC to delete.</span></span>  
  
5.  <span data-ttu-id="c6896-189">Use uno de estos tres conjuntos de código, según la opción de eliminación que resulte apropiada:</span><span class="sxs-lookup"><span data-stu-id="c6896-189">Use one of these three sets of code, depending on which delete option is appropriate:</span></span>  
  
    -   <span data-ttu-id="c6896-190">Para eliminar el registro de la DAC pero dejar la base de datos intacta, use el método `Unmanage()`.</span><span class="sxs-lookup"><span data-stu-id="c6896-190">To delete the DAC registration but leave the database intact, use the `Unmanage()` method.</span></span>  
  
    -   <span data-ttu-id="c6896-191">Para eliminar el registro de la DAC y separar la base de datos, use el método `Uninstall()` y especifique `DetachDatabase`.</span><span class="sxs-lookup"><span data-stu-id="c6896-191">To delete the DAC registration and detach the database, use the `Uninstall()` method and specify `DetachDatabase`.</span></span>  
  
    -   <span data-ttu-id="c6896-192">Para eliminar el registro de la DAC y quitar la base de datos, use el método `Uninstall()` y especifique `DropDatabase`.</span><span class="sxs-lookup"><span data-stu-id="c6896-192">To delete the DAC registration and drop the database, use the `Uninstall()` method and specify `DropDatabase`.</span></span>  
  
### <a name="example-deleting-the-dac-but-leaving-the-database-powershell"></a><span data-ttu-id="c6896-193">Ejemplo para eliminar la DAC y mantener la base de datos (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c6896-193">Example Deleting the DAC but Leaving the Database (PowerShell)</span></span>  
 <span data-ttu-id="c6896-194">En el ejemplo siguiente se elimina una DAC denominada MyApplication mediante el método `Unmanage()` para eliminar la DAC pero para dejar la base de datos intacta.</span><span class="sxs-lookup"><span data-stu-id="c6896-194">The following example deletes a DAC named MyApplication using the `Unmanage()` method to delete the DAC but leave the database intact.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Only delete the DAC definition from msdb, the associated database remains active.  
$dacstore.Unmanage($dacName)  
```  
  
### <a name="example-deleting-the-dac-and-detaching-the-database-powershell"></a><span data-ttu-id="c6896-195">Ejemplo para eliminar la DAC y separar la base de datos (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c6896-195">Example Deleting the DAC and Detaching the Database (PowerShell)</span></span>  
 <span data-ttu-id="c6896-196">En el ejemplo siguiente se elimina una DAC denominada MyApplication mediante el método `Uninstall()` para eliminar la DAC y separar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c6896-196">The following example deletes a DAC named MyApplication using the `Uninstall()` method to delete the DAC and detach the database.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = get-item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Delete the DAC definition from msdb and detach the associated database.  
$dacstore.Uninstall($dacName, [Microsoft.SqlServer.Management.Dac.DacUninstallMode]::DetachDatabase)  
```  
  
### <a name="example-deleting-the-dac-and-dropping-the-database-powershell"></a><span data-ttu-id="c6896-197">Ejemplo para eliminar la DAC y quitar la base de datos (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c6896-197">Example Deleting the DAC and Dropping the Database (PowerShell)</span></span>  
 <span data-ttu-id="c6896-198">En el ejemplo siguiente se elimina una DAC denominada MyApplication mediante el método `Uninstall()` para eliminar la DAC y quitar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c6896-198">The following example deletes a DAC named MyApplication using the `Uninstall()` method to delete the DAC and drop the database.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Delete the DAC definition from msdb and drop the associated database.  
## $dacstore.Uninstall($dacName, [Microsoft.SqlServer.Management.Dac.DacUninstallMode]::DropDatabase)  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6896-199">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c6896-199">See Also</span></span>  
 <span data-ttu-id="c6896-200">[Aplicaciones de capa de datos](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="c6896-200">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="c6896-201">[Aplicaciones de capa de datos](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="c6896-201">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="c6896-202">[Implementar una aplicación de capa de datos](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="c6896-202">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 <span data-ttu-id="c6896-203">[Registrar una base de datos como una DAC](register-a-database-as-a-dac.md) </span><span class="sxs-lookup"><span data-stu-id="c6896-203">[Register a Database As a DAC](register-a-database-as-a-dac.md) </span></span>  
 <span data-ttu-id="c6896-204">[Realizar copias de seguridad y restaurar bases de datos de SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="c6896-204">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="c6896-205">Adjuntar y separar bases de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c6896-205">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../databases/database-detach-and-attach-sql-server.md)  
