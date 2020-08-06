---
title: Guardar y ejecutar el paquete (Asistente para importación y exportación de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.saveschedule.f1
ms.assetid: b582c462-3d7a-4a4c-a2a2-2c79fedab75a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a23f69bf66ca3355f1e1c62cc42d51e4aea3da5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674918"
---
# <a name="save-and-execute-package-sql-server-import-and-export-wizard"></a><span data-ttu-id="2b607-102">Guardar y ejecutar el paquete (Asistente para importación y exportación de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2b607-102">Save and Execute Package (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="2b607-103">Utilice el cuadro de diálogo **Guardar y ejecutar paquete** para ejecutar el paquete inmediatamente, guardarlo para ejecutarlo más tarde o ambos.</span><span class="sxs-lookup"><span data-stu-id="2b607-103">Use the **Save and Execute Package** dialog box to run the package immediately, save it to run later, or both.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b607-104"> Si detiene el paquete antes de que termine la ejecución, éste no se guardará, aunque haya activado la casilla **Guardar** .</span><span class="sxs-lookup"><span data-stu-id="2b607-104">If you stop a package before it finishes running, the package is not saved, even if you selected the **Save** check box.</span></span>  
  
 <span data-ttu-id="2b607-105">Para obtener más información acerca de este asistente, vea [Asistente para importación y exportación de SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2b607-105">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="2b607-106">Para obtener información sobre las opciones para iniciar el asistente, así como los permisos necesarios para ejecutar el asistente correctamente, vea [ejecutar el Asistente para importación y exportación de SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2b607-106">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="2b607-107">La finalidad del Asistente para importación y exportación de SQL Server es copiar datos desde un origen a un destino.</span><span class="sxs-lookup"><span data-stu-id="2b607-107">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="2b607-108">El asistente también puede crear una base de datos y tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="2b607-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="2b607-109">Sin embargo, si tiene que copiar diversas bases de datos o tablas, u otros tipos de objetos de bases de datos, debe utilizar el Asistente para copiar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="2b607-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="2b607-110">Para más información, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2b607-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2b607-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="2b607-111">Options</span></span>  
 <span data-ttu-id="2b607-112">**Ejecutar inmediatamente**</span><span class="sxs-lookup"><span data-stu-id="2b607-112">**Execute immediately**</span></span>  
 <span data-ttu-id="2b607-113">Seleccione esta opción para ejecutar inmediatamente el paquete.</span><span class="sxs-lookup"><span data-stu-id="2b607-113">Select this option to run the package immediately.</span></span>  
  
 <span data-ttu-id="2b607-114">**Guardar el paquete SSIS**</span><span class="sxs-lookup"><span data-stu-id="2b607-114">**Save SSIS Package**</span></span>  
 <span data-ttu-id="2b607-115">Guarde el paquete para ejecutarlo más tarde, con la opción de ejecutarlo inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="2b607-115">Save the package to run later, with the option to run it immediately.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b607-116">En [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] , la opción para guardar el paquete creado por el asistente no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2b607-116">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
 <span data-ttu-id="2b607-117">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="2b607-117">**SQL Server**</span></span>  
 <span data-ttu-id="2b607-118">Seleccione esta opción para guardar el paquete en la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` base de datos.</span><span class="sxs-lookup"><span data-stu-id="2b607-118">Select this option to save the package to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b607-119">Esta opción solo está disponible si ha seleccionado la opción **guardar el paquete SSIS** .</span><span class="sxs-lookup"><span data-stu-id="2b607-119">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="2b607-120">**Sistema de archivos**</span><span class="sxs-lookup"><span data-stu-id="2b607-120">**File system**</span></span>  
 <span data-ttu-id="2b607-121">Seleccione esta opción para guardar el paquete como un archivo con la extensión .dtsx.</span><span class="sxs-lookup"><span data-stu-id="2b607-121">Select this option to save the package as a file that has the .dtsx extension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b607-122">Esta opción solo está disponible si ha seleccionado la opción **guardar el paquete SSIS** .</span><span class="sxs-lookup"><span data-stu-id="2b607-122">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="2b607-123">**Nivel de protección de paquetes**</span><span class="sxs-lookup"><span data-stu-id="2b607-123">**Package protection level**</span></span>  
 <span data-ttu-id="2b607-124">Seleccione un nivel de protección de la lista.</span><span class="sxs-lookup"><span data-stu-id="2b607-124">Select a protection level from the list.</span></span>  
  
 <span data-ttu-id="2b607-125">El nivel de protección determina el método de protección, la contraseña o la clave de usuario, así como el ámbito de protección de paquetes.</span><span class="sxs-lookup"><span data-stu-id="2b607-125">The protection level determines the protection method, the password or user key, and the scope of package protection.</span></span> <span data-ttu-id="2b607-126">La protección puede incluir todos los datos o solo los datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="2b607-126">Protection can include all data or sensitive data only.</span></span> <span data-ttu-id="2b607-127">Para comprender los requisitos y las opciones de seguridad de los paquetes, consulte [Access Control de datos confidenciales en paquetes](../security/access-control-for-sensitive-data-in-packages.md) e [información general sobre seguridad &#40;Integration Services&#41;](../security/security-overview-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="2b607-127">To understand the requirements and options for package security, see [Access Control for Sensitive Data in Packages](../security/access-control-for-sensitive-data-in-packages.md) and [Security Overview &#40;Integration Services&#41;](../security/security-overview-integration-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b607-128">Esta opción solo está disponible si ha seleccionado la opción **guardar el paquete SSIS** .</span><span class="sxs-lookup"><span data-stu-id="2b607-128">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="2b607-129">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="2b607-129">**Password**</span></span>  
 <span data-ttu-id="2b607-130">Escriba una contraseña.</span><span class="sxs-lookup"><span data-stu-id="2b607-130">Type a password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b607-131">Esta opción solo está disponible si se ha establecido la opción **nivel de protección de paquetes** en **cifrar la información confidencial con una contraseña** o **cifrar todos los datos con una contraseña**.</span><span class="sxs-lookup"><span data-stu-id="2b607-131">This option is available only if you have set the **Package protection level** option to either **Encrypt sensitive data with password** or **Encrypt all data with password**.</span></span>  
  
 <span data-ttu-id="2b607-132">**Volver a escribir la contraseña**</span><span class="sxs-lookup"><span data-stu-id="2b607-132">**Retype password**</span></span>  
 <span data-ttu-id="2b607-133">Escriba la contraseña nuevamente.</span><span class="sxs-lookup"><span data-stu-id="2b607-133">Type the password again.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b607-134">Esta opción solo está disponible si se ha establecido la opción **nivel de protección de paquetes** en **cifrar la información confidencial con una contraseña** o **cifrar todos los datos con una contraseña**.</span><span class="sxs-lookup"><span data-stu-id="2b607-134">This option is available only if you have set the **Package protection level** option to either **Encrypt sensitive data with password** or **Encrypt all data with password**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b607-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b607-135">See Also</span></span>  
 <span data-ttu-id="2b607-136">[Execution of Projects and Packages](../packages/run-integration-services-ssis-packages.md)  (Ejecución de proyectos y paquetes)</span><span class="sxs-lookup"><span data-stu-id="2b607-136">[Execution of Projects and Packages](../packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="2b607-137">Guardar paquetes</span><span class="sxs-lookup"><span data-stu-id="2b607-137">Save Packages</span></span>](../save-packages.md)  
  
  
