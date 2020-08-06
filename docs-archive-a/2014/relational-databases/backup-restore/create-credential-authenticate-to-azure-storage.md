---
title: Creación de una credencial - autenticarse en Azure Storage | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backuptourl.createcred.f1
ms.assetid: 0622619d-27c5-4ff0-83e5-cde31648c27a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: afdbf2647c79e07cf3f190ec6710eeb6b7718f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749354"
---
# <a name="create-credential---authenticate-to-azure-storage"></a><span data-ttu-id="02c28-102">Crear credencial - autenticarse en Azure Storage</span><span class="sxs-lookup"><span data-stu-id="02c28-102">Create Credential - Authenticate to Azure Storage</span></span>
  <span data-ttu-id="02c28-103">Use el cuadro de diálogo **Copia de seguridad en URL - Crear credencial** para crear una credencial de SQL.</span><span class="sxs-lookup"><span data-stu-id="02c28-103">Use the **Backup to URL - Create Credential** dialog box to create a new SQL Credential.</span></span>  
  
 <span data-ttu-id="02c28-104">Al utilizar este cuadro de diálogo para crear una credencial, debe proporcionar un certificado de administración de Azure agregado al almacén de certificados local o un perfil de publicación descargado en el equipo para validar la suscripción y la información de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="02c28-104">When using this dialog box to create a credential, you must provide an Azure Management Certificate added to the local certificate store or a publishing profile downloaded to your computer to validate the subscription and the storage account information.</span></span>  
  
 <span data-ttu-id="02c28-105">**Credencial SQL**</span><span class="sxs-lookup"><span data-stu-id="02c28-105">**SQL Credential**</span></span>  
 <span data-ttu-id="02c28-106">Especifique el nombre de la credencial SQL que desea crear.</span><span class="sxs-lookup"><span data-stu-id="02c28-106">Specify the name of the SQL Credential you want to create.</span></span>  
  
## <a name="azure-credentials"></a><span data-ttu-id="02c28-107">Credenciales de Azure</span><span class="sxs-lookup"><span data-stu-id="02c28-107">Azure Credentials</span></span>  
 <span data-ttu-id="02c28-108">**Certificado de administración**</span><span class="sxs-lookup"><span data-stu-id="02c28-108">**Management Certificate**</span></span>  
 <span data-ttu-id="02c28-109">Use esta opción para especificar un certificado del almacén de certificados local que coincida con el certificado de administración de Azure.</span><span class="sxs-lookup"><span data-stu-id="02c28-109">Use this option to specify a certificate from the local certificate store that matches the management certificate from Azure.</span></span> <span data-ttu-id="02c28-110">Para obtener más información sobre el certificado de administración de Azure, vea [Creación y actualización de un certificado de administración para Azure](https://go.microsoft.com/fwlink/?LinkId=320781).</span><span class="sxs-lookup"><span data-stu-id="02c28-110">For more information on Azure management certificate, see [Create and Upload a Management Certificate for Azure](https://go.microsoft.com/fwlink/?LinkId=320781).</span></span>  
  
 <span data-ttu-id="02c28-111">**Suscripción**</span><span class="sxs-lookup"><span data-stu-id="02c28-111">**Subscription**</span></span>  
 <span data-ttu-id="02c28-112">Seleccione, escriba o pegue el identificador de su suscripción de Azure que coincida con el certificado de administración del almacén de certificados local.</span><span class="sxs-lookup"><span data-stu-id="02c28-112">Select, type, or paste your Azure subscription ID that matches the management certificate from the local certificate store.</span></span>  
  
 <span data-ttu-id="02c28-113">**Perfil de publicación**</span><span class="sxs-lookup"><span data-stu-id="02c28-113">**Publishing Profile**</span></span>  
 <span data-ttu-id="02c28-114">Use esta opción si tiene un perfil de publicación descargado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="02c28-114">Use this option if you have a publishing profile downloaded to your computer.</span></span> <span data-ttu-id="02c28-115">Si utiliza esta opción, el identificador de suscripción y el certificado se rellenan de forma automática.</span><span class="sxs-lookup"><span data-stu-id="02c28-115">If you use this option, the subscription ID, and the certificate are auto populated.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="02c28-116">SQL Server admite actualmente la versión 2.0 del perfil de publicación.</span><span class="sxs-lookup"><span data-stu-id="02c28-116">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="02c28-117">Para descargar la versión compatible del perfil de publicación, vea [Descargar perfil de publicación 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="02c28-117">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
  
## <a name="storage-account"></a><span data-ttu-id="02c28-118">Cuenta de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="02c28-118">Storage Account</span></span>  
 <span data-ttu-id="02c28-119">Seleccione la cuenta de almacenamiento que desea usar para almacenar los archivos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="02c28-119">Select the storage account you want to use to store the backup files on.</span></span>  
  
  
