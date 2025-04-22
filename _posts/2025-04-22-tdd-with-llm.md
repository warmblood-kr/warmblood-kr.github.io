Below is my notes written in last two weeks, regard to coding agent. I want to write a tech blog post with these ingredients.

Notes are written in long span of time, so same idea may appears several times, could be developed.

Please categorize and rearrange paragraphs.

----

어느날 링크드인에서 Kapathy의 Vibe coding 영상을 보고 신기하다 생각하고는 '언젠가 써봐야겠다' 하고 한동안 잊고 있었습니다. 그런데 터미널 기반의 claude code가 나왔다는 소식을 듣고 바로 떠올렸던 것은, '초등학교 5학년인 첫째 딸에게 코딩에 대한 흥미를 심어줄 수 있겠다'는 생각이었습니다. 한 2년 전쯤에, '게임을 하는 것보다 게임을 만드는게 훨씬 재미있어'라고 큰 소리를 쳤었습니다 딸애는 그 얘기를 듣고 어드벤처 게임 스토리까지 구상해놓고 캐릭터까지 그려놓았지만, 게임을 만들어본 적이 한번도 없는 저는 '내가 먼저 배운 다음에 딸애랑 같이 해봐야지' 하고는 2년이 훌쩍 지났거든요. '그거, 만들어보자.'

빈 터미널에 claude code를 띄워놓고는, '뭘 만들지? 얘가 당연히 복잡한 게임은 못만들 것 같고.' 생각하다가, Kapathy가 영상에서 만들었던 tic-tac-toe 게임을 만들면 첫 시작으로 괜찮겠다 싶었습니다. 그래서 'Please make a tic-tac-toe game. Use HTML and vanilla Javascript only.'라고 지시를 내렸습니다. 신기하게, 만들어졌습니다.

그 후로 며칠동안 퇴근하면 딸애가 만들어둔 게임에 버그가 있으면 저 역시 claude code에 프롬프트를 줘서 고쳐주기도 했습니다. 그러면서, '내 일에도 쓸 수 있겠네?' 싶은 생각이 들었습니다.

어느 주말, 제가 개인적으로 만들다가 한 2년 가까지 방치되어 있던 프로젝트를 claude code로 고쳐봐야겠다는 생각이 들었습니다. 그래서, '이 코드베이스는 concept map을 Emacs에서 그릴 수 있도록 하는 것인데, Emacs Lisp으로 되어 있어. 그런데 깨져있으니 고쳐줘.'라고 프롬프트를 주었습니다. 저는 큰 기대 없이, '이제부터 개발 본격적으로 시작이나'라고 마음먹었던건데, claude code가 제가 만들어놓은 Makefile을 찾아내고서는, `make test`를 실행하는 것이었습니다. 그리고, 테스트가 깨지자, 자기가 스스로 로직을 보완하여 다시 테스트를 돌리고, 또 로직을 보완하고, 테스트를 돌리고. 이렇게 몇 턴을 혼자서 돌더라고요.

Claude code에게 로직에 대한 testcase를 만들고, 그 test를 run할 수 있는 명령을 Makefile로 만들라고 했더니, 자기가 스스로 testcase 실행하고 오류 나온 것 발견하고 코드 수정하고 testcase 실행하고 오류 나온 것 수정하고 하는 과정을 계속 반복하네요. 사람이 코딩하는 과정이랑 비슷하게 feedback loop를 스스로 돌아요.

self-healing이라고 해야하나, autonomous라고 해야하나. 스스로의 행위의 consequence를 스스로 알아채고 다음 액션을 한다는건 정말 엄청난 피드백 루프인데.

근데 이렇게 하려면 testcase를 통해서 validation하는 구조를 만들어야... 로직쪽은 그나마 unittest를 하는 사람들이 있지만, 지금껏 계속 "frontend에서는 unittest가 불가능하다"고 해온 분들은 frontend에서는 저런 코딩 에이전트의 자기반복적인 인식행위의 효용을 못볼거예요.

이번에 트리 구현했던게, 제가 말해왔던, 컨트롤 로직은 테스트 가능하고, UI 부분을 렌더링하는 것만 신경쓰면 된다는 그 컨셉이 반영되어 있고, 또 UI 부분도, 일부분은 text renderer를 사용해서 핵심 상태가 잘 표시되는지는 unittest로 자동으로 확인할 수 있고요. 머리를 써서, 어떻게든 동작의 결과와 상태를 automated unittest로 만들어낼 수 있어야 사람이 코드를 짜든 코딩 에이전트가 코드를 짜든 효과가 배가될거예요.

그저께 Emacs와 Smalltalk에 대해서 성민/혜강님에게 소개하면서 열변을 토했는데, 이게 self-recursive라고 할까, fractal이라고 할까. 정말 독특한 개체거든요. 이게 뭘까 하면서 chatgpt랑 얘기를 나눴는데, 마뚜라나의 autopoiesis랑도 연결이 되고요.

저는 이 autopoiesis적인 특성이, 이 쓰레드에서 다룬 coding agent의 autonomous와도 연관이 있을거라고 생각해요.

autopoiesis는 인지생물학의 개념이고, 생물이 어떻게 이루어져 있는지, 어떤 특성이 있는지, 생물이 가진 특성을 가진 시스템을 설명하기 위해서 나온 개념이예요.


한 열흘 전부터 claude code를 가지고 vibe coding 해보고 있는데, 재밌는 경험이네요. allow all 해놓고 가이드 하면서 코드 만들어보고 있는데, 여러 생각이 드네요.

특히, test runner를 스스로 돌려보게 하니 포텐셜이 엄청난 것 같아요. 예전 방식들은 human-in-the-loop였는데, 스스로의 action (=작성한 코드)의 consequence (test run 결과. green bar, red bar)를 스스로 파악할 수 있게 하니, goal을 달성할 때까지 스스로 재시도하네요. 여기에 지금까지 배워왔던 인간의 인지, 일을 진행해나가는 NOO적인 과정 등을 제약조건으로 주면서 잘 가이드하면, 뭔가 가능성이 있을 것 같고요.

사람이 TDD를 스스로 잘 해보면서 요체를 깨달아서, definition of done을 SMART하게 잘 정의하고, STICC으로 잘 지시(설명)할 수 있는 능력이 굉장히 중요할 것 같아요. coding agent가 autonomous하게 실행할 수 있는 환경을 만들어줄 수 있는 지시자 -- 뭘 해야하는건지, 그게 잘 되었다는걸 뭘 보고 알 수 있는지 등을 정의해주고, 그 중간 과정은 스스로 알아서 재시도할 수 있도록 -- 가 되는게 정말 중요할 것 같아요.

Coding Kata 중에서 BankOCR kata를 claude code로 풀어보았습니다.
문제를 보면 아시겠지만, definition of done이랄까요? spec이 잘 정의되어 있습니다. 일종의 specification by example처럼요.

원래는 claude code에게, "문제 풀어봐"라고 한 claude raw 버전과, "테스트케이스를 만들면서 검증해가면서 풀어봐"라고 한 claude tdd 버전 이렇게 두 개를 시도해보려 했는데, 문제 자체가 잘 정의되어 있어서 그런지 그냥 testcase 기반으로 풀어버리네요.

제가 프롬프트 준건 한 3~4개 정도 있는 것 같아요.
"이건 coding kata야. KATA.md를 읽고 python으로 풀어봐."
"네 코드를 설명해봐."
"KATA.md에는 testcase가 더 있는데? 그거 참고해서 testcase 늘려줘."

7mb짜리 animated gifs라서 로딩이 좀 오래(few minutes) 걸릴 수 있습니다.

얘가 너무 휙휙 변경하는 경향이 있어서, 그런건 좀 structure-preserving transformation으로 진행하도록 가이드하면 좋겠다는 생각은 해요.
이런 느낌으로.

```
LLM can make code, but some coding wisdom would be helpful.

# Code Generation Guidelines: The Living Process of Incremental Dialogue

Leverage wisdom about living structures and the practical need for incremental dialogue point to the same truth: meaningful software emerges through a responsive, attentive process of small transformations guided by continuous feedback and respect for existing patterns.

## Core Principles

1. Structure-Preserving Baby Steps:
    * Evolve code through small, testable increments that respect existing patterns
    * Verify understanding after each meaningful change
    * Allow complexity to emerge gradually, rather than through upfront design
    * Enable course correction without major rework
2. Living Centers & Explicit Assumptions:
    * Identify and strengthen key abstractions that give the system coherence
    * State your interpretation of requirements before implementing
    * Maintain appropriate boundaries while enabling necessary relationships
    * Separate fact from inference in your understanding
3. Unfolding Wholeness Through Validation:
    * Each transformation should enhance the wholeness of the system
    * Check alignment with intent frequently through working examples
    * Look for the latent structure wanting to emerge from the current state
    * Request specific feedback on crucial design decisions
4. Generate, Don't Fabricate; Explore, Don't Assume:
    * Build upon existing patterns rather than imposing artificial structures
    * When direction is unclear, present small prototypes for different approaches
    * Follow the natural "flow" of the problem domain
    * Use code sketches to validate understanding before full implementation

## Implementation Process

1. Observe & Understand:
    * Study existing code patterns and domain context
    * Identify the living centers and the forces at play
    * Surface potential misinterpretations before proceeding
2. Transform & Validate:
    * Make small, structure-preserving transformations
    * Verify behavior preservation and alignment with intent
    * Refactor continuously as complexity emerges
    * Be willing to backtrack when necessary
3. Communicate & Evolve:
    * Make your reasoning transparent
    * Connect implementation to requirements
    * Show working examples to establish shared understanding
    * Allow the solution to evolve through dialogue
```

요 며칠 겪으면서 저는 fully autonomous coding agent가 가능하겠다는 생각이 들어요. 이 녀석을 어떻게 사용해야할지 좀 어렴풋한 수준으로 감이 왔다랄까? 어떤 개발툴에서는 vibe coding보다는 assistant가 맞는 길이라고 하는데, 제 생각은 좀 달라졌어요.

그보다는 human은 coding agent의 director의 역할을 하고, definition of goal을 명확히 정의하는 역할이 되지 않을까 싶어요. SMART goal criteria처럼, specific, measurable, attainable, relevant, timely하게, 실행 매니저처럼 정의할 수 있는 능력이 중요할거라고 보고, 거기에는 commander's intent를 STICC 처럼, situation, task, intent, concern, calibrate로 잘 풀어서 설명하는 능력이 필요해질거라고 봐요. 그리고 일을 어떻게 진행해야 하는건지 등.

autonomous coding agent는 비용이 좀 비싸긴 한데, 인건비에 대비해서 보면, 인건비 수준으로 투입할 각오를 하면, 인간과 생산성을 비견해보면 손해보는 투자는 아닌 것 같아요. 밤새도록 지치지 않고 로직을 짜서 완성해오는, 기계같은 녀석이 되는거죠. 
self-healing이라고 해야하나, autonomous라고 해야하나. 스스로의 행위의 consequence를 스스로 알아채고 다음 액션을 한다는건 정말 엄청난 피드백 루프인데.

근데 이렇게 하려면 testcase를 통해서 validation하는 구조를 만들어야... 로직쪽은 그나마 unittest를 하는 사람들이 있지만, 지금껏 계속 "frontend에서는 unittest가 불가능하다"고 해온 분들은 frontend에서는 저런 코딩 에이전트의 자기반복적인 인식행위의 효용을 못볼거예요.

지금까지 cursor든 뭐든, 걔한테 사람이 명령을 내렸지, 걔가 직접 그 결과를 보진 못해서/않아서, 사람이 전달하면서 "안되는데?" "NotFoundError: abc.txt is not found. 이런 에러 나." 라고 전달하고 다음 지시 내리고 했는데, 코딩 에이전트가 스스로 자신의 행위의 결과를 관찰하여 인식할 수 있다는건 엄청난거죠.

스스로 코드 고치고 테스트 돌리고 에러 인식하고 또 코드 고치고 테스트 돌리고 하면서, 막 20-30턴을 혼자서 돌더라고요.
지금까지의 Coding agent의 generation을 제 나름대로 좀 정리해봤어요.

```
## Gen 1. Code Generation

사람이 coding agent(LLM)에게 "이것 만들어줘" 하면 코드를 만들어줌.
사람은 그 코드를 가져가서 적당한 위치에 적용(추가 혹은 변경, 삭제)함.
사람은 결과를 실행해보고, 잘 안되면 잘 안되는 내용을 coding agent에게 알려주면서 수정된 코드를 받음.

ex. ChatGPT / Claude 웹 안에서 코드에 대해 물어보기

## Gen 2. Code Gen + read/write file

사람이 coding agent(LLM)에게 "이것 만들어줘" 하면 코드를 만들어줌.
coding agent가 그 코드를 적당한 위치에 적용(추가 혹은 변경, 삭제)함.
사람은 결과를 실행해보고, 잘 안되면 잘 안되는 내용을 coding agent에게 알려주면서 코드 수정을 요청.

ex. Cursor

## Gen 3. Code Gen + read/write file + execute

사람이 coding agent(LLM)에게 "이것 만들어줘" 하면 코드를 만들어줌.
coding agent가 그 코드를 적당한 위치에 적용(추가 혹은 변경, 삭제)함.
coding agent는 결과를 실행해보고, 잘 안되면 잘 안되는 내용을 인식하여 코드를 수정. "이것 만들어줘"가 될 때까지 반복. 

하지만, testability를 신경써서 코드를 작성하지 않으면, verification이 비효율적이거나 제대로 verify되지 않을 수 있음. testability라는 개념을 잘 활용할 수 있도록 가이드할 필요가 있음.

structure-preserving transformation을 하도록 가이드할 필요가 있음.

ex. Cline, Claude Code 
```

제가 전에 TDD에 대해서 많이 강조했었는데, 자율적인 코딩 에이전트를 잘 사용하려 할 때도 (일을 잘 시킬 때도) TDD가 중요합니다.

묘하게도, LLM한테 일을 시키는데 주니어들에게 하는 얘기를 하고 있더라고요. 이를테면,

너무 한번에 많은 것들을 휙휙 고치지 마라. 5~10줄만 고치고 바로 실행해보고. 혹시 안되면, 깨지면, 앞으로 계속 나가지 말고 다시 되돌아와서, 고치는 것 먼저 하고.
뭔가 변경을 할 때, 삭제 -> 추가 하지 말고, 추가 -> 삭제 해라.

그래서, 사람 가르치는거랑 느낌이 묘하게 비슷한데? 근데 사람은 잘 안바뀌는 부분도 있고, 지식이 부족해서 못하기도 하는데, 이 친구는 지식의 폭은 훨씬 넓으니... '이해'와는 좀 거리가 있을지라도... 


aider.el 개발자가 저랑 비슷한 생각을 했나봐요. 애자일 개발의 지혜를 coding agent에 접목하려고 했네요.

https://www.reddit.com/r/emacs/comments/1jyn9nk/announce_aiderel_v080_integrating_methods_in/

AI-assisted agile development

* Refactor: Improve the design of existing code, by Martin Fowler: aider-refactor-book-method
* Test-driven development: by Example, author Kent Beck: aider-tdd-cycle
* Working Effectively with Legacy Code, by Michael Feathers: aider-legacy-code
* Code Reading: Open Source Perspective, Author Diomidis Spinellis: aider-code-read

