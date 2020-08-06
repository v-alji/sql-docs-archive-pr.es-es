---
title: Conectarse a Azure Storage (restauración) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restore.connectstorage.f1
ms.assetid: c0b7d7c8-b878-4b7f-8120-d0c6917b583f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dff9730d6592381b1c8e8a1cf7ee45ad7532a440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677708"
---
# <a name="connect-to-azure-storage-restore"></a><span data-ttu-id="b5fa3-102">Conectar a Azure Storage (restauración)</span><span class="sxs-lookup"><span data-stu-id="b5fa3-102">Connect to Azure Storage (Restore)</span></span>
  <span data-ttu-id="b5fa3-103">El cuadro de diálogo permite especificar la conexión a la información de la cuenta de Azure Storage para recuperar el almacenamiento de archivos en la cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="b5fa3-103">The dialog box allows you to specify the connection to Azure storage account information in order to retrieve the files storage in the Azure storage account.</span></span> <span data-ttu-id="b5fa3-104">Después de especificar la información necesaria, haga clic en **Conectar** para establecer la conexión a Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="b5fa3-104">After specifying the required information, click **Connect** to establish the connection to Azure storage.</span></span>  
  
## <a name="azure-storage-account"></a><span data-ttu-id="b5fa3-105">Cuenta de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="b5fa3-105">Azure Storage Account</span></span>  
 <span data-ttu-id="b5fa3-106">**Cuenta de almacenamiento**</span><span class="sxs-lookup"><span data-stu-id="b5fa3-106">**Storage account**</span></span>  
 <span data-ttu-id="b5fa3-107">Seleccione, escriba o pegue el nombre de la cuenta de Azure Storage que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="b5fa3-107">Select, type or paste the name of the Azure storage account you want to use.</span></span> <span data-ttu-id="b5fa3-108">El cuadro desplegable muestra las cuentas utilizadas previamente.</span><span class="sxs-lookup"><span data-stu-id="b5fa3-108">The drop down box lists the accounts previously used.</span></span>  
  
 <span data-ttu-id="b5fa3-109">**Clave de cuenta**</span><span class="sxs-lookup"><span data-stu-id="b5fa3-109">**Account key**</span></span>  
 <span data-ttu-id="b5fa3-110">Especifique la clave de acceso de la cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="b5fa3-110">Specify the Azure storage account access key.</span></span>  
  
 <span data-ttu-id="b5fa3-111">Casilla**Usar puntos de conexión seguros (HTTPS)**</span><span class="sxs-lookup"><span data-stu-id="b5fa3-111">**Use secure endpoints (HTTPS)** check box</span></span>  
 <span data-ttu-id="b5fa3-112">Seleccione esta opción para establecer una conexión segura con Azure Storage (recomendado).</span><span class="sxs-lookup"><span data-stu-id="b5fa3-112">Select this option to make a secure connection to Azure storage - recommended.</span></span>  
  
 <span data-ttu-id="b5fa3-113">Casilla**Guardar clave de cuenta**</span><span class="sxs-lookup"><span data-stu-id="b5fa3-113">**Save account key** check box</span></span>  
 <span data-ttu-id="b5fa3-114">Active esta casilla si desea que SQL Server recuerde la tecla de acceso para esta cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="b5fa3-114">Select this check box if you want SQL Server to remember the access key for this storage account.</span></span>  
  
### <a name="sql-credential"></a><span data-ttu-id="b5fa3-115">Credencial SQL</span><span class="sxs-lookup"><span data-stu-id="b5fa3-115">SQL Credential</span></span>  
 <span data-ttu-id="b5fa3-116">**Seleccionar una credencial existente**</span><span class="sxs-lookup"><span data-stu-id="b5fa3-116">**Select an existing credential**</span></span>  
 <span data-ttu-id="b5fa3-117">Seleccione una credencial existente de SQL que coincida con la información de clave de cuenta y de cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="b5fa3-117">Select an existing SQL Credential that matches the storage account and account key information.</span></span>  
  
 <span data-ttu-id="b5fa3-118">**Crear una nueva credencial**</span><span class="sxs-lookup"><span data-stu-id="b5fa3-118">**Create a new Credential**</span></span>  
 <span data-ttu-id="b5fa3-119">Seleccione esta opción para crear una nueva credencial utilizando la información de clave de cuenta y de cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="b5fa3-119">Select this option to create a new credential using the storage account and account key information.</span></span> <span data-ttu-id="b5fa3-120">Especifique el nombre de la nueva credencial en el campo **Nombre de credencial** .</span><span class="sxs-lookup"><span data-stu-id="b5fa3-120">Specify the name of the new credential in the **Credential Name** field.</span></span>  
  
  
