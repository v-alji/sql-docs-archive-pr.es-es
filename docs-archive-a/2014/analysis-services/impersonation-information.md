---
title: Información de suplantación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 42319d60-ccd0-46b8-af0b-f0968c390d8a
author: minewiskan
ms.author: owend
ms.openlocfilehash: f9226fdbe8656aecf0f9173976c67ee386040d6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744420"
---
# <a name="impersonation-information"></a><span data-ttu-id="4a03a-102">Información de suplantación</span><span class="sxs-lookup"><span data-stu-id="4a03a-102">Impersonation Information</span></span>
  <span data-ttu-id="4a03a-103">Use la página **Información de suplantación** para especificar las credenciales que Analysis Services utilizará para conectarse al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="4a03a-103">Use the **Impersonation Information** page to specify the credentials that Analysis Services will use to connect to the data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4a03a-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="4a03a-104">Options</span></span>  
 <span data-ttu-id="4a03a-105">**Utilizar un nombre de usuario y una contraseña de Windows específicos**</span><span class="sxs-lookup"><span data-stu-id="4a03a-105">**Use a specific Windows user name and password**</span></span>  
 <span data-ttu-id="4a03a-106">Seleccione esta opción si quiere que el objeto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] use las credenciales de seguridad de una cuenta de usuario de Windows determinada.</span><span class="sxs-lookup"><span data-stu-id="4a03a-106">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials of a specified Windows user account.</span></span> <span data-ttu-id="4a03a-107">Las credenciales especificadas se usarán para el procesamiento, las consultas ROLAP, los enlaces fuera de línea, los cubos locales, los modelos de minería de datos, las particiones remotas, los objetos vinculados y la sincronización del destino al origen.</span><span class="sxs-lookup"><span data-stu-id="4a03a-107">The specified credentials will be used for processing, ROLAP queries, out-of-line bindings, local cubes, mining models, remote partitions, linked objects, and synchronization from target to source.</span></span> <span data-ttu-id="4a03a-108">En cambio, en el caso de las instrucciones OPENQUERY de extensiones de minería de datos (DMX), esta opción se omite y se usarán las credenciales del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="4a03a-108">However, for Data Mining Extensions (DMX) OPENQUERY statements, this option is ignored and the credentials of the current user will be used.</span></span>  
  
 <span data-ttu-id="4a03a-109">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="4a03a-109">**User name**</span></span>  
 <span data-ttu-id="4a03a-110">Escriba el dominio y el nombre de la cuenta de usuario que debe usar el objeto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4a03a-110">Type the domain and name of the user account to be used by the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="4a03a-111">Utilice el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="4a03a-111">Use the following format:</span></span>  
  
 <span data-ttu-id="4a03a-112">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="4a03a-112">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="4a03a-113">Esta opción solo está habilitada si está activada la opción **Usar un nombre de usuario y una contraseña específicos** .</span><span class="sxs-lookup"><span data-stu-id="4a03a-113">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="4a03a-114">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="4a03a-114">**Password**</span></span>  
 <span data-ttu-id="4a03a-115">Escriba la contraseña de la cuenta de usuario que debe usar el objeto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4a03a-115">Type the password of the user account to be used by the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="4a03a-116">Esta opción solo está habilitada si está activada la opción **Usar un nombre de usuario y una contraseña específicos** .</span><span class="sxs-lookup"><span data-stu-id="4a03a-116">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="4a03a-117">**Utilizar cuenta de servicio**</span><span class="sxs-lookup"><span data-stu-id="4a03a-117">**Use the service account**</span></span>  
 <span data-ttu-id="4a03a-118">Seleccione esta opción para que el objeto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] use las credenciales de seguridad asociadas al servicio de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que administra el objeto.</span><span class="sxs-lookup"><span data-stu-id="4a03a-118">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] service that manages the object.</span></span> <span data-ttu-id="4a03a-119">Las credenciales de la cuenta de servicio se usarán para el procesamiento, las consultas ROLAP, las particiones remotas, los objetos vinculados y la sincronización del destino al origen.</span><span class="sxs-lookup"><span data-stu-id="4a03a-119">The service account credentials will be used for processing, ROLAP queries, remote partitions, linked objects, and synchronization from target to source.</span></span> <span data-ttu-id="4a03a-120">No obstante, en el caso de las instrucciones OPENQUERY de las extensiones de minería de datos (DMX), los cubos locales y los modelos de minería de datos, se usarán las credenciales del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="4a03a-120">However, for Data Mining Extensions (DMX) OPENQUERY statements, local cubes, and mining models, the credentials of the current user will be used.</span></span> <span data-ttu-id="4a03a-121">No se admite esta opción para los enlaces fuera de línea.</span><span class="sxs-lookup"><span data-stu-id="4a03a-121">This option is not supported for out-of-line bindings.</span></span>  
  
 <span data-ttu-id="4a03a-122">**Utilizar las credenciales del usuario actual**</span><span class="sxs-lookup"><span data-stu-id="4a03a-122">**Use the credentials of the current user**</span></span>  
 <span data-ttu-id="4a03a-123">Seleccione esta opción para que el objeto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] use las credenciales de seguridad del usuario actual para los enlaces fuera de línea, las instrucciones DMX OPENQUERY, los cubos locales y los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="4a03a-123">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials of the current user for out-of-line bindings, DMX OPENQUERY, local cubes, and mining models.</span></span> <span data-ttu-id="4a03a-124">Esta opción no se admite para el procesamiento, las consultas ROLAP, las particiones remotas, los objetos vinculados y la sincronización del destino al origen.</span><span class="sxs-lookup"><span data-stu-id="4a03a-124">This option is not supported for processing, ROLAP queries, remote partitions, linked objects, and synchronization from target to source.</span></span>  
  
 <span data-ttu-id="4a03a-125">**Adopta**</span><span class="sxs-lookup"><span data-stu-id="4a03a-125">**Inherit**</span></span>  
 <span data-ttu-id="4a03a-126">Seleccione esta opción para usar el comportamiento de suplantación, definido en el nivel de la base de datos, que ha establecido por el administrador del servidor mediante la propiedad de base de datos `DataSourceImpersonation`.</span><span class="sxs-lookup"><span data-stu-id="4a03a-126">Select this option to use the impersonation behavior, defined at the database level, which has been set by the server administrator using the `DataSourceImpersonation` database property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a03a-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a03a-127">See Also</span></span>  
 <span data-ttu-id="4a03a-128">[Orígenes de datos en modelos multidimensionales](multidimensional-models/data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="4a03a-128">[Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="4a03a-129">Orígenes de datos admitidos &#40;&#41;de SSAS multidimensionales</span><span class="sxs-lookup"><span data-stu-id="4a03a-129">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
  
