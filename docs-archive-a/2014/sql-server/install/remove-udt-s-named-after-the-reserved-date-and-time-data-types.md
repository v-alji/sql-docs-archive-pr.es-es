---
title: Quitar UDT&#39;s con el nombre de los tipos de datos de fecha y hora reservados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- time data type [SQL Server], UDTs
- date data type [SQL Server], UDTs
ms.assetid: 48f109af-b1d1-4f03-a7e3-8a0b05ed94e8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 827f060b309a7a620fd448554b074f45d78d3cb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675139"
---
# <a name="remove-udt39s-named-after-the-reserved-date-and-time-data-types"></a>Quitar UDT&#39;s con el nombre de los tipos de datos de fecha y hora reservados
  El Asesor de actualizaciones detectó un tipo definido por el usuario (UDT) que se denomina después de un término reservado para los tipos de datos `date` o `time`.  
  
## <a name="component"></a>Componente  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a>Descripción  
 Los términos usados para los tipos de datos no se deben utilizar como nombres para el Common Language Runtime (CLR) o alias UDTs.  
  
## <a name="corrective-action"></a>Acción correctora  
 Elimine el UDT que se denomina con el tipo de datos y vuelva a crearlo con un nombre no reservado.  
  
  
