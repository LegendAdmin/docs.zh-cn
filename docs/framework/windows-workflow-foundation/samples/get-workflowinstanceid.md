---
title: 获取 WorkflowInstanceId
ms.date: 03/30/2017
ms.assetid: bd7eea3b-1c28-4b84-9a67-003bc553aa81
ms.openlocfilehash: 8cb83fcf15b814b0ca6f7f95f1a9b8eec70185cb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142727"
---
# <a name="get-workflowinstanceid"></a>获取 WorkflowInstanceId
此示例演示如何使用自定义活动 `GetWorkflowInstanceId` 返回工作流实例 ID。  
  
## <a name="demonstrates"></a>演示  
 自定义活动开发，如何访问工作流实例。  
  
## <a name="discussion"></a>讨论区  
 若要获取某个正在运行的工作流的实例 ID，则需要编写代码。 如果您想要编写一个完全声明性的工作流，则需要一个可返回工作流实例 ID 的活动，以便于可在工作流中引用该活动，以提供完全声明性的工作流创作体验。 许多方案需要访问实例 ID：一些示例用于记录或审核目的，或通过将实例 ID 提供回到客户端以供将来关联（例如，通过在 SendReply 活动内部使用此活动），用于执行应用程序级相关性。  
  
 `GetWorkflowInstanceId` 作为一个 <xref:System.Activities.CodeActivity%601> 实现，因为它必须返回 <xref:System.Guid> 类型的值，而且它必须具有对 <xref:System.Activities.CodeActivityContext> 的访问权以获取工作流的实例 ID。 它的实现是相当基本的。  
  
```csharp  
public sealed class GetWorkflowInstanceId : CodeActivity<Guid>  
{  
    protected override Guid Execute(CodeActivityContext context)  
    {  
        return context.WorkflowInstanceId;  
    }  
}
```  
  
> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\GetWorkflowInstanceId`
