# 破茧情报站 · 成品仓（给 Grok / 其他 AI 直接读）

这个文件夹是「破茧情报站」的对外成品，由 leex 维护，情报站每次更新后同步到这里，永远以这里的最新版为准。

- 本文件（README.md）＝规则说明书：打分规则、破茧地图（去哪找、找什么）、当前未读榜单前 10 条。
- deep-dive-2026-11-17.md ＝六路深挖清单：逐条亲开原站核实过的期权策略、退出/对账工具、GEX 自算、AI 评测共 22 条，带成绩口径和坑。
- 用法：按说明书里的地图和严判标准去找新情报；找到的先自己按「能不能真用上」的标准筛一遍，再把名单交回给 leex 复核入库。

---

# 破茧情报站 · 规则说明书（给 Grok / 其他 AI 看的版本）

这是一个每天自动更新的情报站，专盯两条线：AI 工具与 Agent 用法、期权量化。下面是它完整的选源地图、排序权重和版面规则，全部公开，可照着复算和挑错。

## 一、排序权重：什么排前面，什么排后面

每条情报满分 100，由四项相加。默认按总分从高到低排，同分时新的在前。

- **跟你手头的事对不对口（0–40 分）**：占大头。越贴你现在在做的事，分越高。比如能给 Muse 加本事的工具、机器人接 IBKR 的办法，排最前。只是「知道就行」的新功能、小窍门，排后面。每个主题具体多少分，看下面那张表。
- **新不新（两条线算法不一样）（0–25 分）**：这是你定的规矩：要的是真有用的东西，不是越新越好。AI 这边变得快，所以看日期：越新分越高；但要是跟你很对口、又是拿来就能用的东西，哪怕旧一点，也不会被日期拖到最后。期权这边反过来：新不新只占一丁点分，老的好打法、认真的回测、真实的亏钱复盘，照样排前面。
- **出处靠不靠谱（0–20 分）**：源头本身最靠谱（20 分）：比如官方自己发的、GitHub 上的原项目、tastytrade 这种自己做数据的。大家讨论和转述的次一档（14 分）：比如 YouTube、Reddit。其他网站默认 10 分。
- **能不能真用上（逐条严判）（0–15 分）**：这一项改了：不再按类别估，是一条一条看原文判的。原文里真有现成能搬的东西（能装的工具、现成代码、现成数据、能照抄的参数），判「能直接用」，15 分；方法具体但要自己动手改的，判「改一改能用」，10 分；只有结论和经验、没东西可搬的，判「只是看看」，3 分，而且总分最多 55；跟项目接不上的，判「用处不大」，0 分，总分最多 35。另外还有一道范围关：跟期权交易和这个项目都无关的通用 AI 新闻（ERP、社媒管家、推特接口、泛泛盘点那种），直接标「不对口」，总分最多 12 分沉到最底，新抓的干脆不收。这个站主要只要两类：夜航社／期权交易能直接用上的，和 AI 怎么用在期权交易与这套系统上、给 leex 和推进助手加本事的。

### 主题相关性明细（第 ① 项的打分表）

| 主题 | 线 | 相关性分 | 为什么给这个分 |
| --- | --- | --- | --- |
| 能扩展 Muse 的工具 | AI 线 | 40 | 能直接给 Muse 加本事，你正用得上 |
| 交易机器人 / IBKR | 期权线 | 38 | 机器人接 IBKR，正是你系统在啃的活 |
| Codex / 编程 Agent | AI 线 | 36 | 编程帮手怎么写代码，你的推进助手天天要用 |
| AI 交易 Agent | 期权线 | 36 | 你正让 AI 帮忙做交易判断，先看看别人做到哪了 |
| GitHub 开源项目 | AI 线 | 32 | 免费的现成项目，看中了直接装上用 |
| 回测与数据 | 期权线 | 30 | 打法行不行，先拿过去的数据试一遍再上模拟盘 |
| GEX 与关键位 | 期权线 | 28 | 你定铁鹰两边位置，就靠看这类关键价位 |
| 策略与 0DTE 打法 | 期权线 | 26 | 别人的 0DTE 打法，拿来跟夜航社的对照 |
| 亏损复盘 | 期权线 | 24 | 别人是怎么亏光的，看完能少踩坑 |
| AI 平台新功能 | AI 线 | 20 | 平台出了啥新功能，知道就行 |
| AI 使用技巧 | AI 线 | 16 | 用 AI 的小窍门，有空再学 |

### 另外三项的速查

- 新不新（两条线算法不一样）：AI 线 ≤1 天 25 分，≤3 天 20 分，≤7 天 15 分，≤14 天 10 分，≤30 天 5 分，更旧 2 分（按原文发布时间，没有则按抓取时间）；但对口程度 ≥32 分且能不能直接用 ≥12 分的 AI 内容有保底，新不新至少按 12 分算——新或者有用，占一样就能靠前。期权线新不新最高只占 8 分：≤7 天 8 分，≤30 天 7 分，≤90 天 6 分，更旧 5 分——老的好打法、认真的回测、真实的亏钱复盘不因旧被压后；选材时也不按日期筛期权线。
- 出处靠不靠谱：源头本身 20 分（github.com、producthunt.com、openai.com、anthropic.com、tastytrade.com、spotgamma.com、quantconnect.com、optionomega.com、arxiv.org、huggingface.co 等）；大家讨论和转述的 14 分（youtube.com、reddit.com、x.com、*.substack.com、medium.com、dev.to、news.ycombinator.com、bilibili.com 等）；其余 10 分。
- 能不能真用上（2026-11-16 起逐条严判，不再按主题估）：判「能直接用」（原文真有现成工具/代码/数据/参数能搬进项目）15 分；「改一改能用」10 分；「只是看看」3 分且总分封顶 55；「用处不大」0 分且总分封顶 35。还没判过的老条目暂时按旧估算（GitHub 仓库 15、工具类主题 12、机器人/回测主题 10、其余 5），判完即换。另有对口范围关：本站主要只要两类——夜航社／期权交易能直接用上的（core），和 AI 怎么用在期权交易与这套系统上、给 leex 和推进助手加本事的（ai_use）；与期权交易和本项目无关的通用 AI 工具新闻（ERP、社媒管家、推特/YouTube 接口、通用工作台、泛泛盘点）判 off_topic，总分封顶 12 沉底，新抓的直接不收。

## 二、版面为什么这样排

- **最重要的放最上面**：跟写新闻一个道理：先说重点，细节往后放。你哪怕只看三秒，也能带走最要紧的那几条。所以打开先看到「先看这几条」，全量列表在下面。（出处：Sisense：4 Dashboard Design Principles https://www.sisense.com/blog/4-design-principles-creating-better-dashboards/?ref=drawnto.digital）
- **学老报纸：头条放最显眼的地方**：老报纸把大标题放在头版最上面，因为人第一眼就看那里。这站把未读数、刷新按钮和头条都放在页面上头，也是这个道理。（出处：VizMasters：What Newspapers Can Teach Us About Dashboard Design https://vizmasters.substack.com/p/what-newspapers-can-teach-us-about）
- **排顺序就看三样：新不新、重不重要、出处靠不靠谱**：谷歌新闻那类排顺序的公开思路，就是看这几样。这站的四项打分就是照着它改的，每项多少分都写明了，不搞黑箱。（出处：System Design School：News Aggregator System Design https://systemdesignschool.io/problems/news-aggregator/solution）
- **打分规则全摆出来，谁都能自己算**：有个叫 PaperWeb 的自动报纸，把自己的打分办法整页公开。这站学它：规则就摆在页面上，还能一键打包发给 Grok，让它帮你挑错。（出处：PaperWeb：How PaperWeb works https://paperweb.wehack.net/how/）

## 三、破茧地图：去哪找、找什么

原则：
- 看数据派：做市商和机构怎么用统计说话（tastytrade 研究），不只听群里喊单
- 看亏钱的人怎么死的：Reddit 爆仓复盘比成功学更能保命
- 看圈外路子：波动率交易、官方策略指数这些夜航社里没有的打法
- 搜东西全用英文词：中文期权量化资料太浅，深水区都在英文那边

平台：
- B站（两条线）：学教程：AI 工具和期权策略的中文系统课、实操录屏
- 小红书（AI 线）：逛玩法：别人怎么搭配 AI 工具、晒配置和工作流
- YouTube（两条线）：学打法 + 追新：tastytrade、SpotGamma 的期权研究，国外 AI 工具首发讲解
- X（原推特）（两条线）：第一时间：新工具发布、GEX 每日关键位账号、期权大单播报
- Product Hunt（AI 线）：找新工具：每天的上新榜单，AI 产品首发地
- GitHub（两条线）：挖免费开源：能扩展 Muse 的工具、期权量化与回测项目，看星标和更新频率
- Reddit（两条线）：看真实评价和爆仓复盘：r/algotrading、r/options、r/thetagang
- There's An AI For That / Futurepedia（AI 线）：按需求找工具：输入你想干的事，列出一排现成工具
- tastytrade（期权线）：数据派期权研究：用统计和概率说话的策略检验
- SpotGamma / Unusual Whales / OptionStrat（期权线）：GEX、Gamma 翻转位、异动大单和策略图形化工具
- QuantConnect / OptionOmega（期权线）：靠谱回测：期权策略的历史验证平台

每天自动搜索的英文词（每主题一条）：
- [AI 线 / AI 平台新功能] Claude ChatGPT Grok agent mode new features for coding research automation
- [AI 线 / GitHub 开源项目] GitHub open source AI agent tools MCP trading coding repository
- [AI 线 / 能扩展 Muse 的工具] tools that extend AI agents desktop automation MCP server new
- [AI 线 / Codex / 编程 Agent] OpenAI Codex Claude Code AI coding agent workflow tips
- [AI 线 / AI 使用技巧] AI agent workflow for trading research data analysis multi agent orchestration
- [期权线 / 期权策略与 0DTE 打法] SPX 0DTE options strategy iron condor butterfly research
- [期权线 / GEX 与关键位] gamma exposure GEX levels SPX dealer positioning analysis
- [期权线 / 期权回测与数据] options backtesting data providers QuantConnect OptionOmega
- [期权线 / 交易机器人 / IBKR] algorithmic options trading bot IBKR API python
- [期权线 / AI 交易 Agent] AI trading agents options LLM quantitative research
- [期权线 / 期权亏损复盘] options trading blow up loss post mortem lessons reddit

抓取规则：常规刷新一周两次（周一、周四），每次最多新增 14 条，两条线各不超过 7 条，每个主题不超过 3 条；另有手动触发的「全平台深挖」：87 条搜索把 23 个平台和每个主题交叉扫（AI 线和期权线交错排列，任何一段都两条线兼有），单次最多新增 48 条，一轮深挖的目标是累计新增约 72 条——87 条全部至少跑过一遍、或累计新增先达到目标，一轮才结束。深挖带进度记忆：一轮没扫完，下次接着没扫完的地方继续，没轮到的平台在覆盖表里明确标「未扫」；选材不按发布日期筛期权线内容，老的经典策略、扎实回测、真实复盘照样收。深挖同一次运行里会先补全旧条目缺的中文版和逐条分析（一次 30 条量级），并如实报告还剩多少条待补。两种抓取都按原文链接永久去重、永不覆盖用户已标记的状态；搜索结果的标题和来源逐字保留，摘要用大白话中文重写，英文原标题附在条目下方。

## 四、当前看板：未读里排最前的 10 条（导出时刻）

1. 网上的AI工具编程助手能直接用 —— huggingface.co｜https://huggingface.co/docs/hub/en/spaces-agents
一句话：网上的Spaces能变成Claude随手调用的工具。
关键词：编程AI · 现成工具 · 按意思搜 · 直接调用
对读者有什么用（逐条分析）：这一条具体是agents.md让编程AI直接调用Spaces，正对你想给Claude加本事这件事。你可以先找一个转文字这类小工具，让Claude Code试着调用一次。跑通了，再把这种接法搬到推进助手的调度里。
能不能用（严判）：能直接用｜范围：AI 利用｜对得上：给 Muse 加本事
下一步动手：找一个现成Space，把agents.md交给Claude Code，当场试调一次
分数构成：对口程度 40 + 新不新 20 + 出处靠不靠谱 20 + 能不能直接用 15 = 95
2. 10套编程AI外壳大比拼，原始记录全公开 —— huggingface.co｜https://huggingface.co/buckets/joelniklaus/CodingBenchmarkResults
一句话：编程AI强不强别听宣传，翻原始记录自己比
关键词：编程比赛 · AI外壳 · 原始记录 · 选工具
对读者有什么用（逐条分析）：你搭推进助手，正缺调度写法和现成套路。这仓库能看10套外壳咋调度AI干活。挑顺手的学着写，再让编程AI照着跑。
能不能用（严判）：能直接用｜范围：AI 利用｜对得上：推进助手多 AI 协作
下一步动手：把仓库拉进推进助手，挑跑得最稳的外壳记录，照着让编程AI试跑。
分数构成：对口程度 36 + 新不新 20 + 出处靠不靠谱 20 + 能不能直接用 15 = 91
3. 在Mac上同时管四个编程AI —— www.producthunt.com｜https://WWW.PRODUCTHUNT.COM/products/ai-bridge/launches/ai-bridge
一句话：一个工具在Mac上同时管好几个编程AI
关键词：Mac工具 · 多AI并排 · 编程助手 · 一个调度台
对读者有什么用（逐条分析）：你每天在Claude、Codex和Grok之间来回切，这台调度台正对口。先试着让三家同时跑小任务，你只管派活和收活。推进助手的多人分工，也能照这个并排法先跑起来。
能不能用（严判）：能直接用｜范围：AI 利用｜对得上：给 Muse 加本事、推进助手多 AI 协作
下一步动手：装上这个Mac小工具，让Claude、Codex、Grok同开小任务试跑。
分数构成：对口程度 36 + 新不新 20 + 出处靠不靠谱 20 + 能不能直接用 15 = 91
4. 30个MCP工具，个个都查过还在更新 —— bilou26mada.github.io｜https://bilou26mada.github.io/agentic-insider/tools/mcp-servers.html
一句话：30个MCP工具已验过，还在更新能放心挑
关键词：精选三十 · 逐个验过 · 还在更新 · 免费开源
对读者有什么用（逐条分析）：你挑MCP工具最怕挑到没人管的，这30个已经有人替你查过。先看最近还在更新的，再对着推进助手缺的本事挑。这样比自己在GitHub上大海捞针省事多了。
能不能用（严判）：改一改能用｜范围：AI 利用｜对得上：给 Muse 加本事
下一步动手：从30个里挑一个还在更新的。装到Claude上。先拿小活试。
分数构成：对口程度 40 + 新不新 20 + 出处靠不靠谱 20 + 能不能直接用 10 = 90
5. 一个工具让AI也能动手操控电脑 —— dev.to｜https://dev.to/hermestomagent/i-already-control-this-computer-heres-a-tool-that-lets-other-ais-do-it-2nmd
一句话：让AI动鼠标打字的工具，能帮Claude操控电脑
关键词：桌面操控 · 鼠标点击 · 看屏幕 · 敲命令
对读者有什么用（逐条分析）：这个工具是单个现成货，能直接装。它在 GitHub 有 6500 星，就是很多人收藏。推进助手的执行 AI 也能借它点软件干活。
能不能用（严判）：能直接用｜范围：AI 利用｜对得上：给 Muse 加本事、推进助手多 AI 协作
下一步动手：把 Desktop Commander 装给 Muse，先让它点开一个软件并截图确认。
分数构成：对口程度 40 + 新不新 20 + 出处靠不靠谱 14 + 能不能直接用 15 = 89
6. Pi新版火了，现在也能接外挂工具了 —— dev.to｜https://dev.to/ashraf_chowdury09/pi-10-just-hit-1-on-hacker-news-the-agent-that-hated-mcp-now-ships-it-1nkp
一句话：Pi新版能接更多工具了，爱折腾AI的可以试试
关键词：Pi新版 · 外挂工具 · 编程助手 · 热门第一
对读者有什么用（逐条分析）：你搭推进助手正缺调度写法。可以先把Pi 1.0装来试一天。看它接MCP工具顺不顺，再决定要不要留它帮忙写代码。
能不能用（严判）：能直接用｜范围：AI 利用｜对得上：推进助手多 AI 协作、给 Muse 加本事
下一步动手：把Pi 1.0装来试一天，看它接MCP工具顺不顺手
分数构成：对口程度 40 + 新不新 20 + 出处靠不靠谱 14 + 能不能直接用 15 = 89
7. AI编程助手能自己操作电脑了 —— dev.to｜https://dev.to/piekwerk/vercel-agent-desktop-computer-use-for-coding-agents-through-the-accessibility-tree-5fap
一句话：给Claude装双手，它就能点按钮帮你操作电脑
关键词：桌面操作 · 给AI装手 · 免费开源 · 点按钮
对读者有什么用（逐条分析）：你天天重度用Claude，又爱给它装新本事，这个agent-desktop正对口。先让它做开软件、填表这类小事，看它点得稳不稳。稳了再放进推进助手里，让多个AI分工时多一双能动手的手。
能不能用（严判）：能直接用｜范围：AI 利用｜对得上：给 Muse 加本事、推进助手多 AI 协作
下一步动手：装上agent-desktop先试小事。让Claude开软件填表。点得稳再放进推进助手。
分数构成：对口程度 40 + 新不新 20 + 出处靠不靠谱 14 + 能不能直接用 15 = 89
8. 新工具管多个AI一起改代码 —— www.producthunt.com｜https://www.producthunt.com/products/avp/launches/avp
一句话：AVP管多个AI改代码，检查过了才准合并。
关键词：AVP · AI改代码 · 合并检查 · 开源工具
对读者有什么用（逐条分析）：这条讲AVP的单独房间和合并检查。推进助手有调度、编程和监工分工。正好可试它管编程Agent，减少互相踩改动。
能不能用（严判）：改一改能用｜范围：AI 利用｜对得上：推进助手多 AI 协作
下一步动手：给推进助手照着改：每个编程AI单独改一份，合入前先查主版本。
分数构成：对口程度 36 + 新不新 20 + 出处靠不靠谱 20 + 能不能直接用 10 = 86
9. 一个窗口，管一队AI程序员干活 —— www.producthunt.com｜https://www.producthunt.com/products/manyagents/launches/manyagents?comment=5981319
一句话：一个窗口分活给多个AI程序员，还带验收
关键词：一队助手 · 分活干活 · 单独副本 · 专人验收
对读者有什么用（逐条分析）：你的推进助手正好是调度加干活加验收。这款就是摆在眼前的现成样子。可以照它学分活，也学监工怎么挑错。
能不能用（严判）：改一改能用｜范围：AI 利用｜对得上：推进助手多 AI 协作
下一步动手：照它给推进助手加三步：分活给Claude和Codex、各拿副本、最后专人验收。
分数构成：对口程度 36 + 新不新 20 + 出处靠不靠谱 20 + 能不能直接用 10 = 86
10. 给AI挑预测市场工具，先看能不能花真钱 —— www.trendsmcp.ai｜https://www.trendsmcp.ai/blog/best-polymarket-mcp-servers
一句话：挑预测市场插头，练手版花不了真钱更安心
关键词：预测市场 · 模拟练手 · 花不了真钱 · AI插头
对读者有什么用（逐条分析）：pm-trader-mcp最对你的路子，你现在也是先Paper验够了再谈实盘。它拿真价格练假钱，AI下错也不会真亏，还能顺手练AI判断和防重复下单。
能不能用（严判）：能直接用｜范围：AI 利用｜对得上：夜航社 Paper 系统、给 Muse 加本事
下一步动手：给Claude装pm-trader-mcp，拿假钱练AI下单判断。
分数构成：对口程度 40 + 新不新 20 + 出处靠不靠谱 10 + 能不能直接用 15 = 85

注：期权线内容只作情报和思路参考，任何策略先在 Paper 里验证、过回测，不构成下单建议。
