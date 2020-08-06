---
title: 'Lección 1: crear objetos de Azure Storage | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 74edd1fd-ab00-46f7-9e29-7ba3f1a446c5
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: d46c6d22ffd92dbf8035bff140960af8ef56122d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663862"
---
# <a name="lesson-1-create-azure-storage-objects"></a><span data-ttu-id="e0d2b-102">Lección 1: Crear objetos de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="e0d2b-102">Lesson 1: Create Azure Storage Objects</span></span>
  <span data-ttu-id="e0d2b-103">Para poder crear copias de seguridad de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en el almacenamiento en la nube, debe crear primero una cuenta de almacenamiento y después un contenedor de blobs.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-103">Before you can create [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backups on cloud storage, you must first create a storage account, and then a blob container.</span></span> <span data-ttu-id="e0d2b-104">La lección 1 le guía por los pasos necesarios para iniciar sesión en Azure Portal de administración, crear una cuenta de almacenamiento y un contenedor de blobs.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-104">Lesson 1 walks you through the steps of Logging into the Azure Management Portal, creating a storage account and a blob container.</span></span>  
  
## <a name="create-a-storage-account"></a><span data-ttu-id="e0d2b-105">Creación de una cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="e0d2b-105">Create a storage Account</span></span>  
 <span data-ttu-id="e0d2b-106">Para crear una cuenta de almacenamiento desde Azure Portal de administración, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e0d2b-106">To create a storage account from the Azure Management Portal, use the following steps:</span></span>  
  
1.  <span data-ttu-id="e0d2b-107">Inicie sesión en el Portal de administración de Azure con su cuenta.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-107">Log in to the Azure Management Portal using your account.</span></span> <span data-ttu-id="e0d2b-108">Si no tiene una cuenta de Azure, [visite la versión de evaluación gratuita de 3 meses de Azure](https://go.microsoft.com/fwlink/?LinkId=271927).</span><span class="sxs-lookup"><span data-stu-id="e0d2b-108">If you do not have an Azure account, [visit Azure 3-Month free trial](https://go.microsoft.com/fwlink/?LinkId=271927).</span></span>  
  
     <span data-ttu-id="e0d2b-109">![Pantalla de inicio de sesión de Azure](../../2014/tutorials/media/windowazurelogin-backuptocloud.gif "Pantalla de inicio de sesión de Azure")</span><span class="sxs-lookup"><span data-stu-id="e0d2b-109">![Azure Login Screen](../../2014/tutorials/media/windowazurelogin-backuptocloud.gif "Azure Login Screen")</span></span>  
  
2.  <span data-ttu-id="e0d2b-110">Siga las instrucciones paso a paso detalladas [aquí](https://go.microsoft.com/fwlink/?LinkId=271926)para crear una cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-110">Use the step by step instructions detailed [here](https://go.microsoft.com/fwlink/?LinkId=271926), to create a storage account.</span></span>  
  
3.  <span data-ttu-id="e0d2b-111">Vaya a la cuenta de almacenamiento que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-111">Browse to the storage account you created in previous step.</span></span> <span data-ttu-id="e0d2b-112">En el centro inferior de la página web, haga clic en **administrar claves**.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-112">From the bottom center of the web page, click **MANAGE KEYS**.</span></span> <span data-ttu-id="e0d2b-113">Se mostrará la información de cuenta.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-113">The account information is displayed.</span></span> <span data-ttu-id="e0d2b-114">Copie el nombre de la cuenta de almacenamiento y las claves de acceso.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-114">Copy the storage account name, and the Access Keys.</span></span> <span data-ttu-id="e0d2b-115">Esta información es necesaria para crear credenciales almacenadas de SQL.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-115">This information is required to create SQL Stored Credentials.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="e0d2b-116">usa esta información para obtener acceso a la cuenta de almacenamiento y crear copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-116">uses this information to access the storage account and create backups.</span></span>  
  
     <span data-ttu-id="e0d2b-117">![Captura de pantalla de claves de cuenta de Azure Storage](../../2014/tutorials/media/manageaccesskeys-backuptocloud.gif "Captura de pantalla de claves de cuenta de Azure Storage")</span><span class="sxs-lookup"><span data-stu-id="e0d2b-117">![Screen shot of Azure Storage Account Keys](../../2014/tutorials/media/manageaccesskeys-backuptocloud.gif "Screen shot of Azure Storage Account Keys")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0d2b-118">También puede crear una cuenta de almacenamiento mediante programación con las API de REST.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-118">You can also create a storage account programmatically using REST APIs.</span></span> <span data-ttu-id="e0d2b-119">Para obtener más información, vea [Crear cuenta de almacenamiento](https://go.microsoft.com/fwlink/?LinkId=271928).</span><span class="sxs-lookup"><span data-stu-id="e0d2b-119">For more information, see [Create Storage Account](https://go.microsoft.com/fwlink/?LinkId=271928).</span></span>  
  
### <a name="create-a-blob-container"></a><span data-ttu-id="e0d2b-120">Crear un contenedor de blobs</span><span class="sxs-lookup"><span data-stu-id="e0d2b-120">Create a Blob Container</span></span>  
 <span data-ttu-id="e0d2b-121">Los contenedores proporcionan una agrupación de un conjunto de blobs.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-121">A container provides a grouping of a set of blobs.</span></span> <span data-ttu-id="e0d2b-122">Todos los blobs deben estar en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-122">All blobs must be in a container.</span></span> <span data-ttu-id="e0d2b-123">Una cuenta puede contener un número ilimitado de contenedores, pero debe tener al menos un contenedor.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-123">An account can contain an unlimited number of containers, but must have at least one container.</span></span> <span data-ttu-id="e0d2b-124">Un contenedor puede almacenar un número ilimitado de blobs.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-124">A container can store an unlimited number of blobs.</span></span>  
  
 <span data-ttu-id="e0d2b-125">Para crear un contenedor, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e0d2b-125">To create a Container, use the following steps:</span></span>  
  
1.  <span data-ttu-id="e0d2b-126">Seleccione la cuenta de almacenamiento, haga clic en la pestaña **contenedores** y haga clic en **Agregar contenedor** en la parte inferior de la pantalla, que abre un cuadro de diálogo nuevo.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-126">Select the storage account, click the **CONTAINERS** tab and click **ADD CONTAINER** at the bottom of the screen which opens a new dialog box.</span></span>  
  
     <span data-ttu-id="e0d2b-127">![Creación de un contenedor en el portal de administración](../../2014/tutorials/media/backuptocloud.gif "Creación de un contenedor en el portal de administración")</span><span class="sxs-lookup"><span data-stu-id="e0d2b-127">![Creating a Container in the Management Portal](../../2014/tutorials/media/backuptocloud.gif "Creating a Container in the Management Portal")</span></span>  
  
2.  <span data-ttu-id="e0d2b-128">Escriba el nombre del contenedor.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-128">Enter the name for the container.</span></span> <span data-ttu-id="e0d2b-129">Anote el nombre de contenedor que especificó.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-129">Make a note of the container name you specified.</span></span> <span data-ttu-id="e0d2b-130">Esta información se usa en la dirección URL (ruta de acceso al archivo de copia de seguridad) en las instrucciones T-SQL de las lecciones 3 y 4.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-130">This information is used in the URL (path to backup file) in the T-SQL statements in lesson 3 and 4.</span></span>  
  
3.  <span data-ttu-id="e0d2b-131">Seleccione privado para **tipo de acceso**.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-131">Select Private for **Access Type**.</span></span> <span data-ttu-id="e0d2b-132">Se recomienda crear contenedores privados para proteger los archivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-132">We recommend creating private containers for securing your backup files.</span></span>  
  
     <span data-ttu-id="e0d2b-133">![Creación de un nuevo contenedor de blobs](../../2014/tutorials/media/backuptocloud-newblobcontainer.gif "Creación de un nuevo contenedor de blobs")</span><span class="sxs-lookup"><span data-stu-id="e0d2b-133">![Creating a new blob container](../../2014/tutorials/media/backuptocloud-newblobcontainer.gif "Creating a new blob container")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0d2b-134">La autenticación en la cuenta de almacenamiento es necesaria para las copias de seguridad y la restauración de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] incluso aunque elija crear un contenedor público.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-134">Authentication to the storage account is required for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore even if you choose to create a public container.</span></span>  
    >   
    >  <span data-ttu-id="e0d2b-135">También puede crear un contenedor mediante programación con las API de REST.</span><span class="sxs-lookup"><span data-stu-id="e0d2b-135">You can also create a container programmatically using REST APIs.</span></span> <span data-ttu-id="e0d2b-136">Para obtener más información, vea [crear contenedor](https://go.microsoft.com/fwlink/?LinkId=271946).</span><span class="sxs-lookup"><span data-stu-id="e0d2b-136">For more information, see [Create Container](https://go.microsoft.com/fwlink/?LinkId=271946).</span></span>  
  
### <a name="next-lesson"></a><span data-ttu-id="e0d2b-137">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="e0d2b-137">Next Lesson</span></span>  
 <span data-ttu-id="e0d2b-138">[Lección 2: crear una credencial de SQL Server](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="e0d2b-138">[Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
  
