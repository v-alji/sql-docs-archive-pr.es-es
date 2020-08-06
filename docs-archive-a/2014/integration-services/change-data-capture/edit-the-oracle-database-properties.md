---
title: Editar las propiedades de la base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraProp
ms.assetid: 58dc99f1-ee6b-4508-bb66-2bc589611ff7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d3cad2735e6cd6095f9730f3b4e7228526451d34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671132"
---
# <a name="edit-the-oracle-database-properties"></a><span data-ttu-id="14b4a-102">Editar las propiedades de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="14b4a-102">Edit the Oracle Database Properties</span></span>
  <span data-ttu-id="14b4a-103">Use la pestaña Oracle del editor de propiedades para realizar cambios en la descripción que proporcionó en la página Crear base de datos CDC del Asistente para nueva instancia y para realizar cambios en la información de conexión a bases de datos de minería de registros de Oracle.</span><span class="sxs-lookup"><span data-stu-id="14b4a-103">Use the Oracle tab in the Properties editor to make changes to the description you provided in the Create CDC database page in the New Instance wizard and to make changes to the Oracle Log Mining database connection information.</span></span>  
  
 <span data-ttu-id="14b4a-104">A continuación se describe la información de la pestaña **Oracle** .</span><span class="sxs-lookup"><span data-stu-id="14b4a-104">The following describes the information in the **Oracle** tab.</span></span>  
  
 <span data-ttu-id="14b4a-105">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="14b4a-105">**Name**</span></span>  
 <span data-ttu-id="14b4a-106">Nombre de la instancia CDC que especificó en la página Crear base de datos CDC del Asistente para nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="14b4a-106">The name of the CDC Instance that you entered in the Create CDC Database page in the New Instance wizard.</span></span> <span data-ttu-id="14b4a-107">Este campo es de solo lectura y no puede editar esta información.</span><span class="sxs-lookup"><span data-stu-id="14b4a-107">This field is read only and you cannot edit this information.</span></span>  
  
 <span data-ttu-id="14b4a-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="14b4a-108">**Description**</span></span>  
 <span data-ttu-id="14b4a-109">Puede editar la descripción de la nueva instancia o agregar una si no lo hizo al crear la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="14b4a-109">You can edit the description of the new instance or add one if you did not do so when creating the CDC Instance.</span></span>  
  
 <span data-ttu-id="14b4a-110">**Cadena de conexión de Oracle**</span><span class="sxs-lookup"><span data-stu-id="14b4a-110">**Oracle Connect String**</span></span>  
 <span data-ttu-id="14b4a-111">Cadena de conexión de Oracle al equipo que tiene la base de datos de Oracle que está usando.</span><span class="sxs-lookup"><span data-stu-id="14b4a-111">The Oracle connect string to the computer with the Oracle database you are using.</span></span> <span data-ttu-id="14b4a-112">Este campo es de solo lectura y no puede editar esta información.</span><span class="sxs-lookup"><span data-stu-id="14b4a-112">This field is read only and you cannot edit this information.</span></span> <span data-ttu-id="14b4a-113">Esto se debe a que algunos cambios en la cadena de conexión pueden hacer que la instancia CDC de Oracle apunte a otra base de datos de Oracle, lo que dañaría el estado de la instancia CDC almacenada en la tabla **cdc.xdbcdc_config** .</span><span class="sxs-lookup"><span data-stu-id="14b4a-113">This is because some changes to the connect string may point the Oracle CDC Instance to another Oracle database entirely, corrupting the CDC Instance state as stored in the **cdc.xdbcdc_config** table.</span></span> <span data-ttu-id="14b4a-114">Si es necesario realizar pequeños cambios, puede cambiar la cadena de conexión directamente en la tabla de configuración mediante SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="14b4a-114">If minor changes are needed, you can change the connect string directly in the configuration table using SQL Server Management Studio.</span></span>  
  
 <span data-ttu-id="14b4a-115">**Autenticación de minería de registros de Oracle**</span><span class="sxs-lookup"><span data-stu-id="14b4a-115">**Oracle Log Mining Authentication**</span></span>  
 <span data-ttu-id="14b4a-116">Para especificar las credenciales de autenticación de la base de datos de Oracle que contiene el extractor de registros, seleccione una de las opciones siguientes en **Autenticación**:</span><span class="sxs-lookup"><span data-stu-id="14b4a-116">To enter the authentication credentials for the Oracle database that contains the log miner, select one of the following under **Authentication**:</span></span>  
  
-   <span data-ttu-id="14b4a-117">**Autenticación de Windows**: seleccione esta opción para usar las credenciales del dominio de Windows actual.</span><span class="sxs-lookup"><span data-stu-id="14b4a-117">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="14b4a-118">Solo puede usar esta opción si la base de datos de Oracle está configurada para usar la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="14b4a-118">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="14b4a-119">**Autenticación de Oracle**: si selecciona esta opción, debe escribir el **Nombre de usuario** y la **Contraseña** para el usuario en la base de datos de Oracle a la que se está conectando.</span><span class="sxs-lookup"><span data-stu-id="14b4a-119">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Oracle database you are connecting to.</span></span>  
  
 <span data-ttu-id="14b4a-120">Puede ver las propiedades de la base de datos de Oracle en el visor.</span><span class="sxs-lookup"><span data-stu-id="14b4a-120">You can view the Oracle database properties in the viewer.</span></span> <span data-ttu-id="14b4a-121">Cuando se usa el visor, la información es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="14b4a-121">When using the viewer the information is read only.</span></span> <span data-ttu-id="14b4a-122">El visor también incluye una lista de las columnas capturadas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="14b4a-122">The viewer also includes a list of the captured columns in the table.</span></span> <span data-ttu-id="14b4a-123">Para obtener información acerca de cómo obtener acceso al visor, vea [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="14b4a-123">For information on how to access the viewer, see [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14b4a-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14b4a-124">See Also</span></span>  
 <span data-ttu-id="14b4a-125">[Cómo administrar un servicio CDC desde la Consola del diseñador CDC](how-to-manage-a-cdc-service-from-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="14b4a-125">[How to Manage a CDC Service from the CDC Designer Console](how-to-manage-a-cdc-service-from-the-cdc-designer-console.md) </span></span>  
 <span data-ttu-id="14b4a-126">[Conectarse a una base de datos de origen de Oracle](connect-to-an-oracle-source-database.md) </span><span class="sxs-lookup"><span data-stu-id="14b4a-126">[Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md) </span></span>  
 [<span data-ttu-id="14b4a-127">Conectar con Oracle</span><span class="sxs-lookup"><span data-stu-id="14b4a-127">Connect to Oracle</span></span>](connect-to-oracle.md)  
  
  
