---

copyright:
  years: 2015, 2019
lastupdated: "2019-02-28"

subcollection: assistant

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:deprecated: .deprecated}
{:important: .important}
{:note: .note}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# 대화에서 학습
{: #logs}

사용자와 이 대화 스킬을 사용하는 어시스턴트 간의 메시지 목록을 열려면 탐색줄에서 **사용자 대화**를 선택하십시오.
{: shortdesc}

**사용자 대화** 페이지를 열면 기본 보기에 마지막 날의 결과가 나열되며, 최근 결과가 먼저 표시됩니다. 메시지에 사용되는 상위 인텐트(#intent)와 인식되는 모든 엔티티(@entity) 값 및 메시지 텍스트가 사용 가능합니다. 인식되지 않는 인텐트의 경우 표시되는 값은 *관련 없음*입니다. 엔티티가 인식되지 않거나 제공되지 않은 경우 표시되는 값은 *엔티티를 찾을 수 없음*입니다.
![로그 기본 페이지](images/logs_page1.png)

**사용자 대화** 페이지에 사용자와 애플리케이션 간의 총 *메시지* 수를 표시하는 것은 중요합니다. 메시지는 사용자가 애플리케이션에 전송하는 단일 발화(utterance)입니다. 각 대화는 여러 메시지로 구성될 수 있습니다. 따라서 이 **사용자 대화** 페이지의 결과 수는 [개요](/docs/services/assistant?topic=assistant-logs-overview) 페이지에 표시된 대화 수와 다릅니다.

## 로그 한계
{: #logs-limits}

메시지를 보유하는 시간은 {{site.data.keyword.conversationshort}} 서비스 플랜에 따라 다릅니다.

  서비스 플랜                          | 대화 메시지 보유
  ------------------------------------ | ------------------------------------
  프리미엄                             | 지난 90일
  플러스                               | 지난 30일
  표준                                 | 지난 30일
  Lite                                 | 지난 7일

## 메시지 필터링
{: #logs-filter-messages}

*사용자 문장 검색*, *인텐트*, *엔티티* 및 *지난* n*일*을 기준으로 메시지를 필터링할 수 있습니다.

*사용자 문장 검색* - 검색줄에 단어를 입력하십시오. 이렇게 하면 사용자 입력이 검색되지만 애플리케이션의 응답은 검색되지 않습니다.

*인텐트* - 드롭 다운 메뉴를 선택하고 입력 필드에 인텐트를 입력하거나 채워진 목록에서 선택하십시오. 둘 이상의 인텐트를 선택할 수 있으며, 선택한 인텐트를 사용하여 결과를 필터링할 수 있습니다(*관련 없음* 포함).

![인텐트 드롭 다운 메뉴](images/intents_filter.png)

*엔티티* - 드롭 다운 메뉴를 선택하고 입력 필드에 엔티티 이름을 입력하거나 채워진 목록에서 선택하십시오. 둘 이상의 엔티티를 선택할 수 있으며, 선택한 엔티티를 기준으로 결과를 필터링할 수 있습니다. 인텐트 *및* 엔티티를 기준으로 필터링하는 경우 결과에 두 값을 모두 가진 메시지가 포함됩니다. 또한 *엔티티를 찾을 수 없음*으로 결과를 필터링할 수 있습니다.

![엔티티 드롭 다운 메뉴](images/entities_filter.png)

메시지를 업데이트하는 데 약간의 시간이 걸릴 수 있습니다. 해당 컨텐츠를 필터링하려고 시도하기 전에 사용자와 애플리케이션의 상호작용 후 30분 이상을 기다리십시오.

## 개별 메시지 보기
{: #logs-see-message}

각 메시지 항목을 펼쳐서 전체 대화에서 사용자가 말한 내용과 애플리케이션의 응답을 확인할 수 있습니다. 이렇게 하려면 **대화 열기**를 선택하십시오. 해당 대화 내에서 선택한 메시지로 자동으로 이동합니다.

각 대화의 맨 위에 표시되는 시간은 브라우저의 시간대를 반영하도록 현지화됩니다. API 호출을 통해 동일한 대화 로그를 검토하는 경우에 표시되는 시간소인과 다를 수 있습니다. API 로그 호출은 항상 UTC로 표시됩니다.

![대화 패널 열기](images/open_convo.png)

그런 다음 선택한 메시지에 대한 분류를 표시하도록 선택할 수 있습니다.

![분류가 포함된 대화 패널 열기](images/open_convo_classes.png)

## 전체 어시스턴트에서 개선
{: #logs-deploy-id}

대화 스킬 작성은 반복 프로세스입니다. 스킬을 개발하는 동안 *시험 사용* 분할창을 사용하여 서비스가 테스트 입력의 올바른 인텐트 및 엔티티를 인식하는지 확인하고 필요에 따라 수정합니다.

사용자 대화 페이지에서 스킬을 배치하는 데 사용한 어시스턴트와 사용자 간의 실제 상호작용을 분석할 수 있습니다. 이러한 상호작용을 기반으로 정정하여 대화 스킬에서 인텐트 및 엔티티가 인식되는 정확도를 높일 수 있습니다. 사용자가 질문하는 *방법* 또는 사용자가 제출할 수 있는 랜덤 메시지를 정확히 알기 어렵기 때문에 실제 대화를 자주 분석하여 대화 스킬을 개선하는 것이 중요합니다.

여러 어시스턴트를 포함하는 {{site.data.keyword.conversationshort}} 인스턴스의 경우 한 어시스턴트의 대화 스킬에 있는 메시지 데이터를 사용하여 동일한 인스턴스 내의 다른 어시스턴트에에서 사용되는 대화 스킬을 개선하는 것이 유용한 경우가 있습니다.

![프리미엄 플랜만 해당](images/premium0.png) {{site.data.keyword.conversationshort}} 프리미엄 사용자인 경우 선택적으로 여러 프리미엄 인스턴스에서 어시스턴트의 로그 데이터에 액세스할 수 있도록 인스턴스를 구성할 수 있습니다.

예를 들어, *HelpDesk*라는 {{site.data.keyword.conversationshort}} 인스턴스가 있습니다. HelpDesk 인스턴스에 프로덕션 어시스턴트와 개발 어시스턴트가 둘 다 있을 수 있습니다. 개발 어시스턴트에 대한 대화 스킬에서 작업하는 경우 프로덕션 어시스턴트 메시지의 로그를 사용하여 개발 어시스턴트의 대화 스킬을 개선할 수 있습니다.

프로덕션 어시스턴트에 전송된 메시지의 데이터를 사용 중인 경우에도 개발 어시스턴트의 대화 스킬 내에서 수행한 편집은 개발 어시스턴트의 대화 스킬에만 영향을 줍니다.

마찬가지로, 여러 버전의 스킬을 작성하는 경우 한 버전의 메시지 데이터를 사용하여 다른 버전의 훈련 데이터를 개선하려고 할 수 있습니다.

### 데이터 소스 선택
{: #logs-pick-data-source}

*데이터 소스*라는 용어는 고객과 대화 스킬이 배치된 어시스턴트 또는 사용자 정의 애플리케이션 간의 대화에서 컴파일된 로그를 나타냅니다.

*분석* 탭을 열면 현재 대화 스킬과의 사용자 상호작용으로 생성된 메트릭이 표시됩니다. 고객이 현재 스킬을 배치 및 사용하지 않는 경우에는 메트릭이 표시되지 않습니다.

고객과 상호작용한 다른 어시스턴트 또는 사용자 정의 애플리케이션에 추가된 대화 스킬 또는 스킬 버전의 메시지 데이터로 메트릭을 채우려면 다음 단계를 완료하십시오.

1.  **데이터 소스** 필드를 클릭하여 사용할 로그 데이터가 있는 어시스턴트의 목록을 확인하십시오.

    이 목록에는 배치되어 액세스할 수 있는 어시스턴트가 나열됩니다. 해당 옵션에 대한 자세한 정보는 [설명된 *배치 ID 표시*](#logs-deployment-id-explained)를 참조하십시오.

1.  데이터 소스를 선택하십시오.

선택한 데이터 소스에 대한 통계 정보가 표시됩니다.

스킬 버전은 목록에 포함되어 있지 않습니다. 특정 스킬 버전과 연관된 데이터를 가져오려면 특정 스킬 버전이 배치된 어시스턴트에서 사용된 시간 범위를 알아야 합니다. 어시스턴트를 데이터 소스로 선택한 후 메트릭 데이터를 해당 날짜별로 필터링할 수 있습니다.

### 설명된 *배치 ID 표시*
{: #logs-deployment-id-explained}

V1 버전의 API를 사용하는 애플리케이션은 `/message` API를 사용하여 전송된 각 메시지에 배치 ID를 지정해야 합니다. 이 ID는 호출이 수행된 배치된 앱을 식별합니다. 분석 페이지는 이 배치 ID를 사용하여 특정 라이브 애플리케이션과 연관된 로그를 검색하고 표시할 수 있습니다.

V2 버전의 API를 사용하는 어시스턴트 또는 사용자 정의 앱의 경우 각 /message 호출과 함께 시스템 ID 및 스킬 ID가 자동으로 서비스에 포함되므로 배치 ID를 사용하는 대신 어시스턴트 이름으로 데이터 소스를 선택할 수 있습니다.

배치 ID를 추가하기 위해 V1 API 사용자가 이 예에서와 같이 [context ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://cloud.ibm.com/apidocs/assistant?curl=#get-response-to-user-input){: new_window}의 metadata 내부에 deployment 특성을 포함시킵니다.

```json
"context" : {
  "metadata" : {
       "deployment": "HelpDesk-Production"
  }
}
```
{: codeblock}

## 훈련 데이터 개선
{: #logs-fix-data}

실제 사용자 대화의 인사이트를 사용하여 대화 스킬과 연관된 모델을 수정하십시오.

다른 데이터 소스의 데이터를 사용하는 경우 모델에 대한 개선사항은 현재 대화 스킬에만 적용됩니다. **데이터 소스** 필드는 이 대화 스킬을 개선하기 위해 사용 중인 메시지의 소스를 표시하며 페이지의 맨 위에는 변경사항을 적용하는 대화 스킬이 표시됩니다.

### 인텐트 정정
{: #logs-correct-intent}

1.  인텐트를 정정하려면 선택한 #intent 옆에 있는 ![편집](images/edit_icon.png) 편집 아이콘을 선택하십시오.
1.  제공된 목록에서 이 입력에 대한 올바른 인텐트를 선택하십시오.
    - 입력 필드에 입력을 시작하면 인텐트 목록이 필터링됩니다.
    - 또한 이 메뉴에서 **관련 없음으로 표시**를 선택할 수 있습니다. (자세한 정보는 [관련 없음으로 표시](/docs/services/assistant?topic=assistant-intents#intents-mark-irrelevant)를 참조하십시오.) 또는 **인텐트에 대해 훈련하지 않음**을 선택할 수 있습니다. 이 경우 이 메시지를 훈련의 예제로 저장하지 않습니다.

    ![인텐트 선택](images/select_intent.png)
1.  **저장**을 선택하십시오.

    ![인텐트 저장](images/save_intent.png)

    {{site.data.keyword.conversationshort}} 서비스는 사용자 입력을 *현재 상태로* 인텐트에 예제로 추가하도록 지원합니다. 인텐트 훈련 데이터에서 @entity 참조를 예제로 사용 중이고 저장하려는 사용자 메시지에 훈련 데이터의 엔티티 값 또는 동의어가 포함된 경우 나중에 해당 메시지를 편집해야 합니다. 저장한 후 인텐트 페이지에서 메시지를 편집하여 참조하는 엔티티를 대체하십시오. 자세한 정보는 [@Entity를 인텐트 예제로 직접 참조](/docs/services/assistant?topic=assistant-intents#intents-entity-as-example)를 참조하십시오.
    {: tip}

### 엔티티 값 또는 동의어 추가
{: #logs-add-entity}

1.  엔티티 값이나 동의어를 추가하려면 선택한 @entity 옆에 있는 ![편집](images/edit_icon.png) 편집 아이콘을 선택하십시오.
1.  **엔티티 추가**를 선택하십시오.

    ![엔티티 추가](images/add_entity.png)
1.  이제 밑줄이 있는 사용자 입력에서 단어나 구를 선택하십시오.

    ![엔티티 선택](images/select_entity.png)
1.  강조표시된 구를 값으로 추가할 엔티티를 선택하십시오.
    - 입력 필드에 입력을 시작하면 엔티티 및 값 목록이 필터링됩니다.
    - 기존 값에 대한 동의어로 강조표시된 구를 추가하려면 드롭 다운 목록에서 `@entity:value`를 선택하십시오.

    ![엔티티 단어 추가](images/add_entity_word.png)
1.  **저장**을 선택하십시오.

    ![엔티티 저장](images/add_entity_save.png)
