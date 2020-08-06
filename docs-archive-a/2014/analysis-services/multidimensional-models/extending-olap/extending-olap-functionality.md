---
title: Extender la funcionalidad de OLAP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 49a17ff3-94e9-4969-84fc-37d49e63933b
author: minewiskan
ms.author: owend
ms.openlocfilehash: d64d1ac46e2571aa6f8065a8ea42e4cc43aa589e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677897"
---
# <a name="extending-olap-functionality"></a><span data-ttu-id="fd532-102">Extender la funcionalidad de OLAP</span><span class="sxs-lookup"><span data-stu-id="fd532-102">Extending OLAP functionality</span></span>
  <span data-ttu-id="fd532-103">Como programador, puede ampliar Analysis Services escribiendo ensamblados, extensiones personalizadas y procedimientos almacenados que proporcionen la funcionalidad que desea usar y cambiar la finalidad en aplicaciones de base de datos.</span><span class="sxs-lookup"><span data-stu-id="fd532-103">As a programmer, you can extend Analysis Services by writing assemblies, personalized extensions, and stored procedures that provide functionality you want to use and repurpose in multiple database applications.</span></span> <span data-ttu-id="fd532-104">Los ensamblados se usan para ampliar la funcionalidad de los modelos multidimensionales mediante la adición de nuevos procedimientos y funciones al lenguaje MDX o mediante el complemento de personalización.</span><span class="sxs-lookup"><span data-stu-id="fd532-104">Assemblies are used to extend multidimensional models functionality by adding new procedures and functions to the MDX language or by means of the personalization addin.</span></span>  
  
 <span data-ttu-id="fd532-105">Los procedimientos almacenados se pueden usar para llamar a rutinas externas, simplificando el desarrollo y la implementación de bases de datos de Analysis Services al permitir que el código común se desarrolle una vez y se almacene en una sola ubicación.</span><span class="sxs-lookup"><span data-stu-id="fd532-105">Stored procedures can be used to call external routines, simplifying Analysis Services database development and implementation by allowing common code to be developed once and stored in a single location.</span></span> <span data-ttu-id="fd532-106">Los procedimientos almacenados se pueden utilizar para agregar funcionalidades de negocio a las aplicaciones que no sean suministradas por la funcionalidad nativa de MDX.</span><span class="sxs-lookup"><span data-stu-id="fd532-106">Stored procedures can be used to add business functionality to your applications that is not provided by the native functionality of MDX.</span></span>  
  
 <span data-ttu-id="fd532-107">Las personalizaciones son objetos personalizados que se agregan a un cubo para proporcionar un comportamiento que varía según el usuario.</span><span class="sxs-lookup"><span data-stu-id="fd532-107">Personalizations are custom objects that you add to a cube to provide a behavior that varies by user.</span></span> <span data-ttu-id="fd532-108">Las personalizaciones no son objetos permanentes del cubo, sino que la aplicación cliente las aplica dinámicamente durante la sesión del usuario.</span><span class="sxs-lookup"><span data-stu-id="fd532-108">Personalizations are not permanent objects in the cube, but are objects that the client application applies dynamically during the user's session.</span></span> <span data-ttu-id="fd532-109">Los ejemplos incluyen el cambio de la moneda de un valor monetario en función de la persona que tiene acceso a los datos, proporcionando KPI individualizados o una lista de sugerencias de destino para los clientes habituales que compran en línea.</span><span class="sxs-lookup"><span data-stu-id="fd532-109">Examples include changing the currency of a monetary value depending on the person accessing the data, providing individualized KPIs, or a targeted suggestion list for regular customers who purchase online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fd532-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fd532-110">In This Section</span></span>  
 [<span data-ttu-id="fd532-111">Extender OLAP mediante personalizaciones</span><span class="sxs-lookup"><span data-stu-id="fd532-111">Extending OLAP through personalizations</span></span>](extending-olap-through-personalizations.md)  
  
 [<span data-ttu-id="fd532-112">Extensiones de personalización de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="fd532-112">Analysis Services Personalization Extensions</span></span>](analysis-services-personalization-extensions.md)  
  
 [<span data-ttu-id="fd532-113">Definir procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="fd532-113">Defining Stored Procedures</span></span>](../../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
