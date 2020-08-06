---
title: SQLForeignKeys | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLForeignKeys function
ms.assetid: 6c01ce0d-30d7-4c86-8705-3ab254d8a845
author: rothja
ms.author: jroth
ms.openlocfilehash: a61e80867abb8ecb4d2628b74dc9956051c8e4ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671073"
---
# <a name="sqlforeignkeys"></a><span data-ttu-id="7ea2f-102">SQLForeignKeys</span><span class="sxs-lookup"><span data-stu-id="7ea2f-102">SQLForeignKeys</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7ea2f-103">admite las actualizaciones y eliminaciones en cascada a través del mecanismo de restricciones de clave externa.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-103">supports cascading updates and deletes through the foreign key constraint mechanism.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7ea2f-104">devuelve SQL_CASCADE para las columnas UPDATE_RULE o DELETE_RULE si se ha especificado la opción CASCADE en las cláusulas ON UPDATE u ON DELETE de las restricciones FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-104">returns SQL_CASCADE for UPDATE_RULE and/or DELETE_RULE columns if CASCADE option is specified on the ON UPDATE and/or ON DELETE clause of the FOREIGN KEY constraints.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7ea2f-105">devuelve SQL_NO_ACTION para las columnas UPDATE_RULE o DELETE_RULE si se ha especificado la opción NO ACTION en las cláusulas ON UPDATE u ON DELETE de las restricciones FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-105">returns SQL_NO_ACTION for UPDATE_RULE and/or DELETE_RULE columns if NO ACTION option is specified on the ON UPDATE and/or ON DELETE clause of the FOREIGN KEY constraints.</span></span>  
  
 <span data-ttu-id="7ea2f-106">Cuando los valores no válidos están presentes en cualquier parámetro **SQLForeignKeys** , **SQLForeignKeys** devuelve SQL_SUCCESS en ejecución.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-106">When invalid values are present in any **SQLForeignKeys** parameter, **SQLForeignKeys** returns SQL_SUCCESS on execution.</span></span> <span data-ttu-id="7ea2f-107">**SQLFetch** devuelve SQL_NO_DATA si se usan valores no válidos en estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-107">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="7ea2f-108">**SQLForeignKeys** se puede ejecutar en un cursor de servidor estático.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-108">**SQLForeignKeys** can be executed on a static server cursor.</span></span> <span data-ttu-id="7ea2f-109">Un intento de ejecutar **SQLForeignKeys** en un cursor actualizable (dinámico o Keyset) devuelve SQL_SUCCESS_WITH_INFO que indica que se ha cambiado el tipo de cursor.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-109">An attempt to execute **SQLForeignKeys** on an updatable (dynamic or keyset) cursor returns SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="7ea2f-110">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client admite la información de informes de tablas en servidores vinculados aceptando un nombre de dos partes para los parámetros *FKCatalogName* y *PKCatalogName* : *Linked_Server_Name. Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="7ea2f-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *FKCatalogName* and *PKCatalogName* parameters: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea2f-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ea2f-111">See Also</span></span>  
 <span data-ttu-id="7ea2f-112">[SQLForeignKeys función)](https://go.microsoft.com/fwlink/?LinkId=59344) </span><span class="sxs-lookup"><span data-stu-id="7ea2f-112">[SQLForeignKeys Function](https://go.microsoft.com/fwlink/?LinkId=59344) </span></span>  
 [<span data-ttu-id="7ea2f-113">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="7ea2f-113">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
