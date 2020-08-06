---
title: Información de suplantación (cuadro de diálogo del Asistente para la importación de tablas) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.impersonationinfo.f1
ms.assetid: bee7eee5-0650-41f1-a372-5076ae97a58c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5300f8b6106a7f29f51018b4e039c2a8c28aa729
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744421"
---
# <a name="impersonation-information-dialog-box-table-import-wizard"></a><span data-ttu-id="aedb2-102">Cuadro de diálogo Información de suplantación (Asistente para la importación de tablas)</span><span class="sxs-lookup"><span data-stu-id="aedb2-102">Impersonation Information Dialog Box (Table Import Wizard)</span></span>
  <span data-ttu-id="aedb2-103">Use la página **Información de suplantación** para especificar las credenciales que [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] utilizará para conectarse al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="aedb2-103">Use the **Impersonation Information** page to specify the credentials that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] will use to connect to the data source.</span></span> <span data-ttu-id="aedb2-104">Para más información sobre la suplantación de credenciales, vea [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="aedb2-104">For more information about credentials impersonation, see [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="aedb2-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="aedb2-105">Options</span></span>  
 <span data-ttu-id="aedb2-106">**Nombre de usuario y contraseña específicos de Windows**</span><span class="sxs-lookup"><span data-stu-id="aedb2-106">**Specific Windows user name and password**</span></span>  
 <span data-ttu-id="aedb2-107">Seleccione esta opción para que el modelo tabular utilice las credenciales de seguridad de una cuenta de usuario de Windows determinada.</span><span class="sxs-lookup"><span data-stu-id="aedb2-107">Select this option to have the tabular model use the security credentials of a specified Windows user account.</span></span>  
  
 <span data-ttu-id="aedb2-108">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="aedb2-108">**User name**</span></span>  
 <span data-ttu-id="aedb2-109">Escriba el dominio y el nombre de la cuenta de usuario que debe usarse.</span><span class="sxs-lookup"><span data-stu-id="aedb2-109">Type the domain and name of the user account to be used.</span></span> <span data-ttu-id="aedb2-110">Utilice el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="aedb2-110">Use the following format:</span></span>  
  
 <span data-ttu-id="aedb2-111">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="aedb2-111">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="aedb2-112">Esta opción solo está habilitada si está activada la opción **Usar un nombre de usuario y una contraseña específicos** .</span><span class="sxs-lookup"><span data-stu-id="aedb2-112">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="aedb2-113">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="aedb2-113">**Password**</span></span>  
 <span data-ttu-id="aedb2-114">Escriba la contraseña de la cuenta de usuario que debe usar el objeto del modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="aedb2-114">Type the password of the user account to be used by the Tabular model.</span></span>  
  
 <span data-ttu-id="aedb2-115">Esta opción solo está habilitada si está activada la opción **Usar un nombre de usuario y una contraseña específicos** .</span><span class="sxs-lookup"><span data-stu-id="aedb2-115">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="aedb2-116">**Cuenta de servicio**</span><span class="sxs-lookup"><span data-stu-id="aedb2-116">**Service account**</span></span>  
 <span data-ttu-id="aedb2-117">Seleccione esta opción para usar las credenciales de seguridad asociadas al servicio de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que administra el modelo.</span><span class="sxs-lookup"><span data-stu-id="aedb2-117">Select this option to use the security credentials associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] service that manages the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aedb2-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aedb2-118">See Also</span></span>  
 [<span data-ttu-id="aedb2-119">Suplantación &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="aedb2-119">Impersonation &#40;SSAS Tabular&#41;</span></span>](tabular-models/impersonation-ssas-tabular.md)  
  
  
