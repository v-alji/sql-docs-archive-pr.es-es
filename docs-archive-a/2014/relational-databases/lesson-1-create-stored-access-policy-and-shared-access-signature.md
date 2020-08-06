---
title: 'Lección 2: Crear una directiva en el contenedor y generar una clave de firma de acceso compartido (SAS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 41674d9d-8132-4bff-be4d-85a861419f3d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab209f08d53b25a4791ef675e6fb6b78cab115f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749306"
---
# <a name="lesson-2-create-a-policy-on-container-and-generate-a-shared-access-signature-sas-key"></a><span data-ttu-id="4b3fc-103">Lección 2:</span><span class="sxs-lookup"><span data-stu-id="4b3fc-103">Lesson 2.</span></span> <span data-ttu-id="4b3fc-104">Crear una directiva en el contenedor y generar una clave de firma de acceso compartido (SAS)</span><span class="sxs-lookup"><span data-stu-id="4b3fc-104">Create a policy on container and generate a Shared Access Signature (SAS) key</span></span>
  <span data-ttu-id="4b3fc-105">En esta lección, aprenderá a crear una directiva en el contenedor de blobs y también a generar una clave SAS.</span><span class="sxs-lookup"><span data-stu-id="4b3fc-105">In this lesson, you will learn how to create a policy on the Blob container and also generate a SAS key.</span></span>  
  
 <span data-ttu-id="4b3fc-106">Una directiva de acceso almacenada proporciona un nivel de control adicional sobre las firmas de acceso compartidas en el servidor.</span><span class="sxs-lookup"><span data-stu-id="4b3fc-106">A stored access policy provides an additional level of control over shared access signatures on the server side.</span></span> <span data-ttu-id="4b3fc-107">Una firma de acceso compartido es un URI que concede derechos de acceso restringidos a los contenedores, los blobs, las colas y las tablas.</span><span class="sxs-lookup"><span data-stu-id="4b3fc-107">A shared access signature is a URI that grants restricted access rights to containers, blobs, queues, and tables.</span></span> <span data-ttu-id="4b3fc-108">Al utilizar esta nueva mejora, debe crear una directiva en un contenedor con derechos de lectura, escritura y enumeración.</span><span class="sxs-lookup"><span data-stu-id="4b3fc-108">When using this new enhancement, you need to create a policy on a container with read, write, and list rights.</span></span>  
  
 <span data-ttu-id="4b3fc-109">Puede crear una directiva y una firma de acceso compartido mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b3fc-109">You can create a policy and a shared access signature by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="4b3fc-110">Operaciones de la API de REST de Azure: [crear contenedor](https://msdn.microsoft.com/library/azure/dd179468.aspx), [establecer ACL del contenedor](https://msdn.microsoft.com/library/azure/dd179391.aspx)y [obtener ACL del contenedor](https://msdn.microsoft.com/library/azure/dd179469.aspx).</span><span class="sxs-lookup"><span data-stu-id="4b3fc-110">Azure REST API operations: [Create Container](https://msdn.microsoft.com/library/azure/dd179468.aspx), [Set Container ACL](https://msdn.microsoft.com/library/azure/dd179391.aspx), and [Get Container ACL](https://msdn.microsoft.com/library/azure/dd179469.aspx).</span></span>  
  
-   <span data-ttu-id="4b3fc-111">[Método CloudBlobContainer. GetSharedAccessSignature](https://docs.microsoft.com/dotnet/api/microsoft.azure.storage.blob.cloudblobcontainer.getsharedaccesssignature) en el SDK de Azure.</span><span class="sxs-lookup"><span data-stu-id="4b3fc-111">[CloudBlobContainer.GetSharedAccessSignature Method](https://docs.microsoft.com/dotnet/api/microsoft.azure.storage.blob.cloudblobcontainer.getsharedaccesssignature) in the Azure SDK.</span></span>  
  
    ```  
  
       string signature = blob.GetSharedAccessSignature(new SharedAccessPolicy()   
        {   
            // Specify the expiration time for the signature.   
            SharedAccessExpiryTime = DateTime.Now.Years(1),   
            // Specify the permissions granted by the signature.    
            Permissions = SharedAccessPermissions.Write | SharedAccessPermissions.Read   
        });  
  
    ```  
  
-   <span data-ttu-id="4b3fc-112">Una herramienta de Azure Explorer de terceros, como [Explorador de Azure Storage](https://azurestorageexplorer.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="4b3fc-112">A third-party Azure explorer tool, such as [Azure Storage Explorer](https://azurestorageexplorer.codeplex.com/).</span></span>  
  
 <span data-ttu-id="4b3fc-113">**Lección siguiente:**</span><span class="sxs-lookup"><span data-stu-id="4b3fc-113">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="4b3fc-114">Lección 3: Crear una credencial de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4b3fc-114">Lesson 3: Create a SQL Server Credential</span></span>](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)  
  
