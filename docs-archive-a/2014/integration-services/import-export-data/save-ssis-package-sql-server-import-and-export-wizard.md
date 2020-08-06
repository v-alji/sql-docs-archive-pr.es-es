---
title: Guardar el paquete SSIS (Asistente para importación y exportación de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.savedtspackage.f1
ms.assetid: 7bf8ac6a-5599-43ab-bf5c-e072c11b85a0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d4e582558a1f86b18d935fcc6235ba5839faa031
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674914"
---
# <a name="save-ssis-package-sql-server-import-and-export-wizard"></a><span data-ttu-id="95e11-102">Guardar el paquete SSIS (Asistente para importación y exportación de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="95e11-102">Save SSIS Package (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="95e11-103">Use la página **guardar el paquete SSIS** para asignar un nombre, describir y guardar un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] paquete de Integration Services ( [!INCLUDE[ssIS](../../includes/ssis-md.md)] ) en la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` base de datos o en un archivo que tenga la extensión. DTSX.</span><span class="sxs-lookup"><span data-stu-id="95e11-103">Use the **Save SSIS Package** page to name, describe, and save a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) package to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` database or to a file that has the .dtsx extension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95e11-104">En [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] , la opción para guardar el paquete creado por el asistente no está disponible.</span><span class="sxs-lookup"><span data-stu-id="95e11-104">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
 <span data-ttu-id="95e11-105">Para obtener más información acerca de este asistente, vea [Asistente para importación y exportación de SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="95e11-105">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="95e11-106">Para obtener información sobre las opciones para iniciar el asistente y sobre los permisos necesarios para ejecutar el asistente correctamente, vea [ejecutar el Asistente para importación y exportación de SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="95e11-106">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="95e11-107">La finalidad del Asistente para importación y exportación de SQL Server es copiar datos desde un origen a un destino.</span><span class="sxs-lookup"><span data-stu-id="95e11-107">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="95e11-108">El asistente también puede crear una base de datos y tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="95e11-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="95e11-109">Sin embargo, si tiene que copiar diversas bases de datos o tablas, u otros tipos de objetos de bases de datos, debe utilizar el Asistente para copiar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="95e11-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="95e11-110">Para más información, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="95e11-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="95e11-111">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="95e11-111">Static Options</span></span>  
 <span data-ttu-id="95e11-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="95e11-112">**Name**</span></span>  
 <span data-ttu-id="95e11-113">Escriba un nombre único para el paquete.</span><span class="sxs-lookup"><span data-stu-id="95e11-113">Provide a unique name for the package.</span></span>  
  
 <span data-ttu-id="95e11-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="95e11-114">**Description**</span></span>  
 <span data-ttu-id="95e11-115">Escriba una descripción para el paquete.</span><span class="sxs-lookup"><span data-stu-id="95e11-115">Provide a description for the package.</span></span> <span data-ttu-id="95e11-116">Como práctica recomendada, describa el paquete en función de su objetivo para que los paquetes se documenten por sí mismos y su mantenimiento resulte sencillo.</span><span class="sxs-lookup"><span data-stu-id="95e11-116">As a best practice, describe the package in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="95e11-117">**Destino**</span><span class="sxs-lookup"><span data-stu-id="95e11-117">**Target**</span></span>  
 <span data-ttu-id="95e11-118">Vea el destino (de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o un archivo) especificado previamente como archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="95e11-118">View the target ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or file) that was previously specified for the destination file.</span></span>  
  
## <a name="target-dynamic-options"></a><span data-ttu-id="95e11-119">Opciones dinámicas de destino</span><span class="sxs-lookup"><span data-stu-id="95e11-119">Target Dynamic Options</span></span>  
  
### <a name="target--sql-server"></a><span data-ttu-id="95e11-120">Destino = SQL Server</span><span class="sxs-lookup"><span data-stu-id="95e11-120">Target = SQL Server</span></span>  
 <span data-ttu-id="95e11-121">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="95e11-121">**Server name**</span></span>  
 <span data-ttu-id="95e11-122">Una vez que haya seleccionado un destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], escriba o seleccione el nombre del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="95e11-122">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, type or select the destination server name.</span></span>  
  
 <span data-ttu-id="95e11-123">**Utilizar autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="95e11-123">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="95e11-124">Una vez que haya seleccionado un destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], especifique si desea conectarse al servidor a través de la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="95e11-124">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, specify whether to connect to the server by using Windows Integrated Authentication.</span></span> <span data-ttu-id="95e11-125">Éste es el método de autenticación preferido.</span><span class="sxs-lookup"><span data-stu-id="95e11-125">This is the preferred authentication method.</span></span>  
  
 <span data-ttu-id="95e11-126">**Utilizar autenticación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="95e11-126">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="95e11-127">Una vez que haya seleccionado un destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], especifique si desea conectarse al servidor a través de la autenticación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95e11-127">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, specify whether to connect to the server by using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="95e11-128">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="95e11-128">**User name**</span></span>  
 <span data-ttu-id="95e11-129">Una vez que haya seleccionado un destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y que haya especificado la autenticación de SQL Server, escriba el nombre de usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95e11-129">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, and have specified SQL Server Authentication, type the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user name.</span></span>  
  
 <span data-ttu-id="95e11-130">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="95e11-130">**Password**</span></span>  
 <span data-ttu-id="95e11-131">Una vez que haya seleccionado un destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y que haya especificado la autenticación de SQL Server, escriba la contraseña de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95e11-131">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, and have specified SQL Server Authentication, type the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] password.</span></span>  
  
### <a name="target--file-system"></a><span data-ttu-id="95e11-132">Destino = Sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="95e11-132">Target = File System</span></span>  
 <span data-ttu-id="95e11-133">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="95e11-133">**File name**</span></span>  
 <span data-ttu-id="95e11-134">Cuando haya seleccionado un destino de archivo, escriba la ruta de acceso del archivo de destino o use el botón **examinar** .</span><span class="sxs-lookup"><span data-stu-id="95e11-134">When you have selected a file destination, type the path for the destination file, or use the **Browse** button.</span></span>  
  
 <span data-ttu-id="95e11-135">**Browse**</span><span class="sxs-lookup"><span data-stu-id="95e11-135">**Browse**</span></span>  
 <span data-ttu-id="95e11-136">Cuando haya seleccionado un destino de archivo, vaya al archivo de destino mediante el cuadro de diálogo **Guardar paquete** .</span><span class="sxs-lookup"><span data-stu-id="95e11-136">When you have selected a file destination, browse to the destination file by using the **Save Package** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e11-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95e11-137">See Also</span></span>  
 [<span data-ttu-id="95e11-138">Guardar paquetes</span><span class="sxs-lookup"><span data-stu-id="95e11-138">Save Packages</span></span>](../save-packages.md)  
  
  
