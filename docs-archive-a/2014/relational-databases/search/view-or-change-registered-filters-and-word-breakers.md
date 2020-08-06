---
title: Ver o cambiar los filtros y separadores de palabras registrados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text search [SQL Server], word breakers
- full-text search [SQL Server], filters
- filters [full-text search]
- word breakers [full-text search]
ms.assetid: f88c54df-b1aa-4701-807f-dc92c32363fd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79ad7f1f7df15fed21a132bbe253adc7185d8c06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745165"
---
# <a name="view-or-change-registered-filters-and-word-breakers"></a><span data-ttu-id="3e23a-102">Ver o cambiar los filtros y separadores de palabras registrados</span><span class="sxs-lookup"><span data-stu-id="3e23a-102">View or Change Registered Filters and Word Breakers</span></span>
  <span data-ttu-id="3e23a-103">Después de instalar o desinstalar filtros o separadores de palabras en un sistema, los cambios no se aplican automáticamente en las instancias de servidor.</span><span class="sxs-lookup"><span data-stu-id="3e23a-103">After any word breakers or filters are installed or uninstalled on a system, the changes do not automatically take effect on server instances.</span></span> <span data-ttu-id="3e23a-104">En este tema se describe cómo ver los filtros o separadores de palabras actualmente registrados y cómo registrar filtros y separadores de palabras recién instalados en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e23a-104">This topic describes how to view the currently registered word breaker or filters and how to register newly installed word breakers and filters on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-view-a-list-of-languages-whose-word-breakers-are-currently-registered"></a><span data-ttu-id="3e23a-105">Para ver una lista de idiomas con separadores de palabras actualmente registrados</span><span class="sxs-lookup"><span data-stu-id="3e23a-105">To view a list of languages whose word breakers are currently registered</span></span>  
  
1.  <span data-ttu-id="3e23a-106">Use la vista de catálogo [sys.fulltext_languages](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) , tal y como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="3e23a-106">Use the [sys.fulltext_languages](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) catalog view, as follows:</span></span>  
  
    ```  
    SELECT * FROM sys.fulltext_languages;   
    ```  
  
### <a name="to-view-a-list-of-the-filters-that-are-currently-registered"></a><span data-ttu-id="3e23a-107">Para ver una lista de los filtros actualmente registrados</span><span class="sxs-lookup"><span data-stu-id="3e23a-107">To view a list of the filters that are currently registered</span></span>  
  
1.  <span data-ttu-id="3e23a-108">Use el procedimiento almacenado del sistema [sp_help_fulltext_system_components](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) , tal y como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="3e23a-108">Use the [sp_help_fulltext_system_components](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) system stored procedure, as follows:</span></span>  
  
    ```  
    EXEC sp_help_fulltext_system_components 'filter';    
    ```  
  
### <a name="to-register-newly-installed-word-breakers-and-filters"></a><span data-ttu-id="3e23a-109">Para registrar filtros y separadores de palabras recién instalados</span><span class="sxs-lookup"><span data-stu-id="3e23a-109">To register newly installed word breakers and filters</span></span>  
  
1.  <span data-ttu-id="3e23a-110">Use el procedimiento almacenado del sistema [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql) para actualizar la lista de idiomas, tal y como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="3e23a-110">Use the [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql) system stored procedure to update the list of languages, as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'update_languages';   
    ```  
  
### <a name="to-unregister-uninstalled-word-breakers-and-filters"></a><span data-ttu-id="3e23a-111">Para anular el registro de filtros y separadores de palabras instalados</span><span class="sxs-lookup"><span data-stu-id="3e23a-111">To unregister uninstalled word breakers and filters</span></span>  
  
1.  <span data-ttu-id="3e23a-112">Use **sp_fulltext_service** para actualizar la lista de idiomas, tal y como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="3e23a-112">Use the **sp_fulltext_service** to update the list of languages, as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'update_languages'  
    ```  
  
2.  <span data-ttu-id="3e23a-113">Use **sp_fulltext_service** para reiniciar los procesos de host de demonio de filtro (fdhost.exe), tal y como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="3e23a-113">Use the **sp_fulltext_service** to restart the filter daemon host processes (fdhost.exe), as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'restart_all_fdhosts';  
    ```  
  
### <a name="to-replace-existing-word-breakers-or-filters-when-installing-new-ones"></a><span data-ttu-id="3e23a-114">Para reemplazar los filtros o separadores de palabras existentes al instalar filtros o separadores de palabras nuevos</span><span class="sxs-lookup"><span data-stu-id="3e23a-114">To replace existing word breakers or filters when installing new ones</span></span>  
  
1.  <span data-ttu-id="3e23a-115">Cuando se prepare para instalar un archivo DLL que contenga nuevos filtros o separadores de palabras, compruebe que tenga un nombre de archivo distinto de cualquiera de los archivos DLL existentes instalados en su instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="3e23a-115">When preparing to install a DLL file that contains new word breakers or filters, verify that it has a different filename from any of the existing DLL files installed on your server instance.</span></span>  
  
2.  <span data-ttu-id="3e23a-116">Copie el nuevo archivo DLL en el directorio que contiene los archivos DLL estándar de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="3e23a-116">Copy the new DLL file into the directory containing the standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] DLL files for the server instance.</span></span> <span data-ttu-id="3e23a-117">La ubicación predeterminada es:</span><span class="sxs-lookup"><span data-stu-id="3e23a-117">The default location is:</span></span>  
  
     <span data-ttu-id="3e23a-118">C:\Archivos de programa\Microsoft SQL Server\MSSQL.*nombre_instancia*\MSSQL\Binn</span><span class="sxs-lookup"><span data-stu-id="3e23a-118">C:\Program Files\Microsoft SQL Server\MSSQL.*instance_name*\MSSQL\Binn</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3e23a-119">Se recomienda encarecidamente que solamente cargue componentes firmados y comprobados.</span><span class="sxs-lookup"><span data-stu-id="3e23a-119">We highly recommend that you load only signed and verified components.</span></span> <span data-ttu-id="3e23a-120">También se recomienda que ejecute el servicio del iniciador de FDHOST (MSSQLFDLauncher) con la menor cantidad de privilegios posible.</span><span class="sxs-lookup"><span data-stu-id="3e23a-120">Also, we recommend that you run the FDHOST Launcher (MSSQLFDLauncher) Service with the least possible privileges.</span></span>  
  
3.  <span data-ttu-id="3e23a-121">Instale los nuevos filtros o separadores de palabras.</span><span class="sxs-lookup"><span data-stu-id="3e23a-121">Install the new word breaker or filters.</span></span>  
  
     <span data-ttu-id="3e23a-122">**Para instalar y cargar IFilters de Microsoft Filter Pack**</span><span class="sxs-lookup"><span data-stu-id="3e23a-122">**To install and load Microsoft Filter Pack IFilters**</span></span>  
  
    -   [<span data-ttu-id="3e23a-123">Cómo registrar IFilters de Microsoft Filter Pack con SQL Server</span><span class="sxs-lookup"><span data-stu-id="3e23a-123">How to register Microsoft Filter Pack IFilters with SQL Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=130439)  
  
4.  <span data-ttu-id="3e23a-124">Use **sp_fulltext_service** para cargar los filtros y separadores de palabras recién instalados en la instancia del servidor, tal y como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="3e23a-124">Use **sp_fulltext_service** to load newly installed word breakers and filters in the server instance, as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service @action='load_os_resources', @value=1;  
    ```  
  
5.  <span data-ttu-id="3e23a-125">Use **sp_fulltext_service** para actualizar la lista de idiomas, tal y como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="3e23a-125">Use **sp_fulltext_service** to update the list of languages, as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service 'update_languages';  
    ```  
  
6.  <span data-ttu-id="3e23a-126">Reinicie los procesos de host de demonio de filtro (fdhost.exe) mediante **sp_fulltext_service** , tal y como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="3e23a-126">Restart the filter daemon host processes (fdhost.exe), using **sp_fulltext_service** as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service 'restart_all_fdhosts';   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3e23a-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3e23a-127">See Also</span></span>  
 <span data-ttu-id="3e23a-128">[Establecer la cuenta del servicio para el selector del demonio de filtro completo](set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="3e23a-128">[Set the Service Account for the Full-text Filter Daemon Launcher](set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 <span data-ttu-id="3e23a-129">[Configurar y administrar filtros para búsquedas](configure-and-manage-filters-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="3e23a-129">[Configure and Manage Filters for Search](configure-and-manage-filters-for-search.md) </span></span>  
 [<span data-ttu-id="3e23a-130">Configurar y administrar separadores de palabras y lematizadores para la búsqueda</span><span class="sxs-lookup"><span data-stu-id="3e23a-130">Configure and Manage Word Breakers and Stemmers for Search</span></span>](configure-and-manage-word-breakers-and-stemmers-for-search.md)  
  
  
