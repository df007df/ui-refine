# 来源与维护边界

首版整理于 2026-10-04，依据已完成的源码研究，采用独立编写的工作流与平台摘要。未打包上游运行时、未复制整套 playbook；来源记录支持后续复核，不是运行依赖。普通任务按入口读取相应内置参考即可。

## 核心来源

| 来源与冻结快照 | 借鉴 | 保留的边界 |
| --- | --- | --- |
| [oil-ui](https://github.com/oil-oil/oil-ui/tree/205e7fa0551bdfa718a0abb1e5f5c551b9f9b22a)，0.12.0，MIT | 品类/主任务、现有方向与小改动分流、中文排版、真实基线、有限评审、视觉/交互分别验收 | 自包含方法；不继承更新/推广脚本；免费版的代码/状态实践需由项目及本技能补充 |
| [Impeccable](https://github.com/pbakaus/impeccable/tree/e103efe779e2dd01274dabae83531fef00bf2563)，Apache-2.0 | 任务模式、专项精修、设计真源、状态恢复、共享组件提取、原生指引及证据意识 | 24 个 Agent 命令主要是模型流程；61 条 registry 规则不表示对所有平台/引擎全覆盖；首版未集成 Rust/live/comp 工具 |

选取了研究清单的 S/C/V/I/R/Q/N/K/CW/AW 等模块，并合并为通用流程及平台参考；166 个研究条目不是本技能的 166 个独立自动化功能。

## 扩展参考

| 来源 | 快照/来源范围 | 本技能使用方式 |
| --- | --- | --- |
| [UI UX Pro Max](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/tree/09170eec67eefd46a7ae85de61b40c194020f997) | 冻结源码，MIT | 可选领域/栈检索；不强制替换现有规范 |
| [taste-skill](https://github.com/Leonxlnx/taste-skill/tree/ce26fc25c0e5e8cab638f883de62d9a86ee5e45b) | 冻结源码，MIT | 可选视觉尺度；按任务采用 |
| `apple-design` | 已安装本地技能，未核验上游 commit；入口 SHA-256 `11840b24a11d7f94f39c6aaab074750ae4e4de4ef54ee4b1dd97e16ebd485e61` | 交互手感和减少动态效果；Web 示例需平台适配 |
| `shadcn-ui` | 已安装本地技能，未核验上游 commit；入口 SHA-256 `2ddfe599ac2ba631ca019f7b6e37ee5df9cd34f83fc016f6ea9d4ba5bbfa0304` | 当前 React 项目的合适组件原语 |
| `wxt-browser-extensions` | 已安装本地技能，49 条指引；入口 SHA-256 `a92a1232432bdc613cf495f1abe9e4b24680f151b9be2baabe0ccc575ca15caf` | Chrome 载体、消息/storage、注入与生命周期；纠正 session 与跨重启需求的不一致 |
| `design-taste-frontend` | 已安装本地技能，未核验上游 commit；入口 SHA-256 `aa194351b246b8b4799099d4ed7b033d29eab6e6e3d58d8d2172978be7b3ec89` | 营销/作品集/改版的可选风格；不覆盖后台或复杂数据 UI |

## 可核查平台事实

- popup 的焦点关闭及独立脚本要求：[Chrome popup](https://developer.chrome.com/docs/extensions/develop/ui/add-popup)。
- 扩展 session/local/sync 的生命周期：[Chrome storage](https://developer.chrome.com/docs/extensions/reference/api/storage)。
- MV3 extension pages 与 sandbox pages 的脚本策略：[Chrome CSP](https://developer.chrome.com/docs/extensions/reference/manifest/content-security-policy)。
- `NativeComponentCapturer` 的实际范围：[Impeccable component_capture.rs](https://github.com/pbakaus/impeccable/blob/e103efe779e2dd01274dabae83531fef00bf2563/crates/cli/src/component_capture.rs)，实现走 Chromium/CDP 网页截图，不提供原生 iOS/Android 捕获。

这些记录对应研究快照与核验日期，不能替代未来项目依赖和当前 API 文档。引用时核实实际载体、版本和配置；源码说明、文字评估、Web 运行与 Chrome/原生 App E2E 分别报告。

## 后续扩展

有明确实际收益时，再接入方案比较生成器、确定性检测器、实时变体写回或稿件还原工具。每项先定义支持平台、输入输出、运行依赖、成本、写回/恢复和失败边界，使用真实样例验证。当前八份参考不承诺这些工具已经集成或可自动执行。
