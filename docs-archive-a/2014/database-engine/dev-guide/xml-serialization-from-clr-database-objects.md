---
title: Serialización XML de objetos de base de datos CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- serialization
- XML serialization [CLR integration]
- common language runtime [SQL Server], XML serialization
- XmlSerializer class
ms.assetid: ac84339b-9384-4710-bebc-01607864a344
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ee93ee4b7bf9cba3f11b329244d4523636cb7704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746445"
---
# <a name="xml-serialization-from-clr-database-objects"></a><span data-ttu-id="39a87-102">Serialización XML de objetos de base de datos de CLR</span><span class="sxs-lookup"><span data-stu-id="39a87-102">XML Serialization from CLR Database Objects</span></span>
  <span data-ttu-id="39a87-103">La serialización XML se requiere para dos situaciones:</span><span class="sxs-lookup"><span data-stu-id="39a87-103">XML serialization is required for two scenarios:</span></span>  
  
-   <span data-ttu-id="39a87-104">Invocar los servicios web desde los objetos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="39a87-104">Invoking Web Services from common language runtime (CLR) objects.</span></span>  
  
-   <span data-ttu-id="39a87-105">Convertir un tipo definido por el usuario (UDT) en XML.</span><span class="sxs-lookup"><span data-stu-id="39a87-105">Converting a user-defined type (UDT) to XML.</span></span>  
  
 <span data-ttu-id="39a87-106">La realización de la serialización XML invocando la clase `XmlSerializer` genera normalmente un ensamblado de serialización adicional que se sobrecarga en el proyecto con el ensamblado de origen.</span><span class="sxs-lookup"><span data-stu-id="39a87-106">Performing XML serialization by invoking the `XmlSerializer` class normally generates an additional serialization assembly that is overloaded into the project with the source assembly.</span></span> <span data-ttu-id="39a87-107">Sin embargo, por razones de seguridad, esta sobrecarga está deshabilitada en CLR.</span><span class="sxs-lookup"><span data-stu-id="39a87-107">However, for security purposes, this overload is disabled in the CLR.</span></span> <span data-ttu-id="39a87-108">Por lo tanto, para llamar a un servicio web o realizar la conversión de UDT a XML dentro [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de, el ensamblado se debe crear manualmente mediante una herramienta denominada **Sgen.exe** proporcionado con el .NET Framework que genera los ensamblados de serialización necesarios.</span><span class="sxs-lookup"><span data-stu-id="39a87-108">Therefore, to call a web service or perform conversion from UDT to XML inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the assembly must be created manually using a tool called **Sgen.exe** provided with the .NET Framework that generates the necessary serialization assemblies.</span></span> <span data-ttu-id="39a87-109">Al invocar `XmlSerializer`, se debe crear el ensamblado de serialización manualmente siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="39a87-109">When invoking `XmlSerializer`, the serialization assembly must be created manually by following these steps:</span></span>  
  
1.  <span data-ttu-id="39a87-110">Ejecute la herramienta de **Sgen.exe** que se proporciona con el SDK de .NET Framework para crear el ensamblado que contiene los serializadores XML para el ensamblado de origen.</span><span class="sxs-lookup"><span data-stu-id="39a87-110">Run the **Sgen.exe** tool that is provided with the .NET Framework SDK to create the assembly containing the XML serializers for the source assembly.</span></span>  
  
2.  <span data-ttu-id="39a87-111">Registre el ensamblado generado en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la instrucción `CREATE ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="39a87-111">Register the generated assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the `CREATE ASSEMBLY` statement.</span></span>  
  
 <span data-ttu-id="39a87-112">Para obtener información sobre los errores que puede recibir al realizar la serialización XML, vea el siguiente artículo de Soporte técnico de Microsoft: ["no se puede cargar el ensamblado de serialización generado dinámicamente"](https://support.microsoft.com/kb/913668).</span><span class="sxs-lookup"><span data-stu-id="39a87-112">For information about errors that you may receive when performing XML serialization, see the following Microsoft Support article: ["Cannot load dynamically generated serialization assembly"](https://support.microsoft.com/kb/913668).</span></span>  
  
 <span data-ttu-id="39a87-113">Para obtener información sobre los tipos de datos no admitidos por XMLSerializer, consulte Compatibilidad con enlaces del esquema XML en .NET Framework en la documentación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="39a87-113">For information on data types that are not supported by XMLSerializer, see XML Schema Binding Support in the .NET Framework in the .NET Framework documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a87-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39a87-114">See Also</span></span>  
 <span data-ttu-id="39a87-115">[Acceso a datos desde objetos de base de datos CLR](../../relational-databases/clr-integration/data-access/data-access-from-clr-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="39a87-115">[Data Access from CLR Database Objects](../../relational-databases/clr-integration/data-access/data-access-from-clr-database-objects.md) </span></span>  
 [<span data-ttu-id="39a87-116">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="39a87-116">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-assembly-transact-sql)  
  
  
