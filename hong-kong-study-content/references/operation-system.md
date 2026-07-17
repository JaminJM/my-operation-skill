# Hong Kong Study Content Operation System

Use this reference for operation decisions before or around content production.

## Workspace Operation Files

Default operation files live outside the skill folder so the user can update them over time:

- `operations/account-stage.md`: current account stage, platform constraints, baseline data, and strategy bias.
- `operations/content-reviews/YYYY-MM-DD-内容数据复盘.md`: saved content performance reviews.
- `operations/monthly-plans/YYYY-MM-运营规划.md`: saved monthly content plans.

Before topic judgment, topic planning, monthly planning, or data review, read `operations/account-stage.md` if it exists. If it is missing, infer conservatively from available context and suggest creating it.

## Workflow 0: Operation Judgment Before Production

Run this before turning a user-provided topic into publishable content, and before recommending topics when the user asks what to write.

Judge the topic from six dimensions:

- 用户需求: Does it answer a real student/parent anxiety or decision?
- 搜索价值: Is it likely to be searched, saved, or discovered later?
- 时效性: Is there current seasonal, policy, ranking, application, visa, or employment relevance?
- 长期价值: Will it remain useful after the immediate publishing window?
- 转化价值: Does it attract readers with real consultation potential, not only curiosity traffic?
- 当前帐号阶段适配: Does it fit the account's current scale, platform signals, and publishing limits?

Use a 1-5 score for each dimension. Then give one clear decision:

- `建议做`: total score 22-30, or one dimension is strategically important enough to justify production.
- `改角度后做`: total score 17-21, or the topic has demand but the current angle is too broad, too generic, too late, or too weak for conversion.
- `暂缓`: total score 13-16, or it depends on data/policy timing that is not ready.
- `不建议做`: total score 12 or below, or the topic is mainly self-expression, low demand, low search, and low conversion.

If the decision is `建议做` or `改角度后做`, state the recommended content angle, primary platform, secondary platform, visual strategy, and whether to proceed into the requested content workflow.

If the decision is `暂缓` or `不建议做`, do not automatically produce the full content package. Briefly explain why and offer 2-3 better replacement angles. If the user explicitly insists, proceed while preserving the judgment note.

For full content packages, save the operation judgment as:

```text
context/<选题名称>/00-选题运营判断.md
```

For narrow single-output writing requests, include a concise operation judgment in the chat or `sources.md` only if useful. Do not create extra files unless the user asks for a full package or wants the judgment archived.

## Current Early-Stage Bias

When `operations/account-stage.md` classifies the account as early-stage or cold-start, prefer topics that can prove demand quickly:

- High-intent searchable topics: applications, deadlines, requirements, visa, IANG, employment, budget, school/program choices.
- Saveable visual topics: rankings, comparison tables, timelines, checklists, "who is suitable", "what to prepare".
- Seasonal topics: application round timing, new ranking releases, policy updates, graduation/employment windows.
- Parent/student decision topics with concrete scenarios and tradeoffs.

Be cautious with:

- Broad brand-view topics such as "为什么选择香港留学" unless tied to a specific decision moment.
- Low-search opinion essays.
- Overly niche policy details without current search demand.
- Pure sales or institution-introduction posts.
- Topics that can get views but have weak consultation intent, unless the goal is explicitly exposure testing.

## Workflow 10: Content Data Review

Use this when the user provides performance data or asks for content复盘, data analysis, title analysis, account diagnosis, or next-step recommendations.

Default review cadence:

- `48小时快检`: For each new post/article, review after about 48 hours. Focus on title, cover/first image, opening hook, initial distribution, and whether the post deserves a quick follow-up or cover/title adjustment.
- `周复盘`: Once per week, review all posts from the last 7 days. Focus on topic signals, cover/title patterns, save/comment/private-message signals, and next week's content tests.
- `月度深复盘`: Once per month, review WeChat and Xiaohongshu together. Focus on account-stage assumptions, content pillars, audience response, conversion quality, and next-month planning.
- `季度方向复盘`: Every 3 months or after enough data, revisit audience positioning, topic mix, conversion path, and whether the account has moved beyond cold start.

Expected fields:

```text
标题
平台
发布时间
内容类型
目标受众
封面/首图文字或截图描述
阅读量/观看量
曝光量（如有）
点赞
收藏
转发
评论
主页访问/新增关注（如有）
咨询
发布时间后 48h 数据（如有）
发布时间后 7d 数据（如有）
备注
```

If the user provides only some fields, analyze what is available and mark missing fields as unknown. Do not block the review unless title or performance data is absent.

Create a dated review file by default:

```text
operations/content-reviews/YYYY-MM-DD-内容数据复盘.md
```

Review structure:

For `48小时快检`:

1. 基础判断: 是否进入基础流量池，数据是否明显低于账号常态.
2. 标题/封面判断: 是标题不够清楚、封面不够停顿，还是题目本身弱.
3. 内容承接判断: 观看高但收藏低、收藏高但观看低、评论/私信是否有意向.
4. 立即动作: keep, change cover/title for future, make follow-up, reply/comment引导, or stop.

For `周复盘`:

1. 数据概览: platform, number of posts, date range, missing data.
2. 单篇表现判断: high, middle, low performers with reasons.
3. 标题/封面判断: which title and first-image patterns attracted views, saves, consultations, or failed.
4. 内容类型判断: which topics fit the current account and which do not.
5. 受众判断: which audience segments responded: student, parent, application executor, IANG/employment, visa/identity, low-age/dependant family.
6. 下周测试: 3-5 concrete topic/cover/format tests.

For `月度深复盘`:

1. 平台差异: WeChat and Xiaohongshu should be judged separately.
2. 内容支柱判断: keep, increase, reduce, stop, or update topic types.
3. 搜索与保存判断: which topics have long-tail search/save value.
4. 转化判断: which posts brought consultation or high-intent signals.
5. 帐号阶段判断: whether current account-stage assumptions still hold.
6. 下月方向: content pillars, publishing rhythm, update/republish list.
7. 可执行动作: 3-7 concrete actions for the next 2-4 weeks.

Useful ratios when data permits:

- WeChat read-to-follower rate = 阅读量 / 粉丝数.
- Engagement rate = (点赞 + 收藏 + 转发) / 阅读量或观看量.
- Consultation rate = 咨询 / 阅读量或观看量.
- Save tendency = 收藏 / 阅读量或观看量, especially for Xiaohongshu.
- Comment/private-message signal = 评论 + 私信 + 咨询, judged qualitatively when volume is small.

Signal interpretation:

- High views + low saves: topic or hook works, but content may lack saveable value.
- Low views + high save rate: content has value but title, cover, or distribution needs work.
- High saves + comments/private messages: create follow-up posts and improve conversion path.
- Low views + low saves + no comments: revise angle, title, cover, or stop repeating that format.
- WeChat low reads but high consultation quality: keep as trust asset and adapt hooks for Xiaohongshu.

Do not overinterpret tiny samples. For small accounts, judge directionally and use labels such as "初步信号", "样本太小", and "需要继续测试".

## Workflow 11: Monthly Operation Planning

Use this when the user asks for next month planning, account planning, publishing schedule, content calendar, or "下个月做什么".

Before planning, read:

- `operations/account-stage.md`
- recent `operations/content-reviews/` files if any
- `topic-bank/香港留学选题库.md`
- recent `context/` topics to avoid repetition

Respect known constraints:

- WeChat currently has a monthly limit of 4 articles.
- Xiaohongshu currently has no strict monthly post limit.

Default plan output:

1. Current account diagnosis.
2. Next-month goal: exposure, search capture, saves, consultation, or trust building.
3. WeChat four-article plan with priority, angle, target reader, and visual need.
4. Xiaohongshu plan with a higher testing frequency and reusable material from WeChat.
5. Update/republish list.
6. Data checkpoints and what the user should report back.

Save planning output by default:

```text
operations/monthly-plans/YYYY-MM-运营规划.md
```

For early-stage accounts, use WeChat for trust-building and searchable long-form assets. Use Xiaohongshu to test hooks, rankings, comparison images, and saveable visual formats more frequently.

## Workflow 12: Content Update Mechanism

Use this when the user asks what needs updating, when producing plans, and before reusing old content.

Prioritize updates when:

- Annual rankings or datasets have a newer version, such as QS 2027 replacing QS 2026.
- Official policy, visa, IANG, immigration, tuition, scholarship, or application requirements changed.
- Application season timing changed.
- A previous content asset still has search value but uses old examples, old year labels, or outdated screenshots.
- A high-performing Xiaohongshu visual topic can be refreshed with the new year or new data.

Update decision labels:

- `立即更新重发`: old year/policy may mislead readers or new version has clear search demand.
- `本月更新`: still useful and likely to capture search, but not urgent.
- `观察`: update depends on whether a new official source or ranking is released.
- `不用更新`: evergreen logic remains valid and the old version is not misleading.

When updating old content, search `context/` first. Prefer creating a new version folder or `-v2` files instead of overwriting old work silently.
