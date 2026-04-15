<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>星云紫微专属14主星人格测试</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "Microsoft YaHei", sans-serif;
        }
        body {
            background-color: #f5f7fa;
            color: #333;
            padding: 20px 0;
        }
        .container {
            max-width: 800px;
            margin: 0 auto;
            background: #fff;
            border-radius: 12px;
            box-shadow: 0 2px 15px rgba(0,0,0,0.05);
            padding: 30px 20px;
        }
        .title {
            text-align: center;
            font-size: 24px;
            font-weight: 700;
            color: #4a3f69;
            margin-bottom: 10px;
        }
        .subtitle {
            text-align: center;
            font-size: 15px;
            color: #666;
            margin-bottom: 30px;
        }
        .step {
            text-align: center;
            font-size: 16px;
            color: #4a3f69;
            margin-bottom: 20px;
            font-weight: 600;
        }
        .question {
            font-size: 18px;
            margin-bottom: 15px;
            line-height: 1.5;
        }
        .options {
            display: flex;
            flex-direction: column;
            gap: 12px;
            margin-bottom: 30px;
        }
        .option {
            padding: 15px 20px;
            border: 1px solid #e0e0e0;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            border-color: #8a7cc3;
            background-color: #f8f7ff;
        }
        .option.selected {
            background-color: #f0edff;
            border-color: #8a7cc3;
            color: #4a3f69;
            font-weight: 600;
        }
        .btn {
            display: block;
            width: 100%;
            padding: 15px;
            background-color: #8a7cc3;
            color: #fff;
            border: none;
            border-radius: 8px;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.3s ease;
            margin-top: 20px;
        }
        .btn:hover {
            background-color: #7163a8;
        }
        .btn:disabled {
            background-color: #ccc;
            cursor: not-allowed;
        }
        #result-page {
            display: none;
            text-align: center;
        }
        .personality-type {
            font-size: 32px;
            font-weight: 700;
            color: #4a3f69;
            margin: 20px 0;
        }
        .personality-name {
            font-size: 20px;
            color: #666;
            margin-bottom: 30px;
        }
        .result-desc {
            text-align: left;
            line-height: 1.8;
            font-size: 16px;
            margin-bottom: 20px;
            padding: 20px;
            background-color: #f8f7ff;
            border-radius: 8px;
        }
        .dimension {
            display: flex;
            justify-content: space-between;
            margin: 15px 0;
            padding: 10px;
            background-color: #fafafa;
            border-radius: 6px;
        }
        .dimension span {
            font-weight: 600;
            color: #4a3f69;
        }
        .restart-btn {
            background-color: #fff;
            color: #8a7cc3;
            border: 1px solid #8a7cc3;
            margin-top: 30px;
        }
        .restart-btn:hover {
            background-color: #f8f7ff;
        }
        .loading {
            display: none;
            text-align: center;
            padding: 50px 0;
            font-size: 18px;
            color: #4a3f69;
        }
        /* 适配小屏幕 */
        @media (max-width: 500px) {
            .container {
                padding: 20px 15px;
            }
            .title {
                font-size: 22px;
            }
            .question {
                font-size: 16px;
            }
            .option {
                padding: 12px 15px;
                font-size: 14px;
            }
            .btn {
                padding: 12px;
                font-size: 16px;
            }
            .personality-type {
                font-size: 28px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 class="title">星云紫微专属SBTI16型人格测试</h1>
        <p class="subtitle">解锁你的专属人格，读懂真实的自己 | 星云紫微出品</p>

        <!-- 测试步骤提示 -->
        <div class="step" id="step-indicator">第1题 / 共28题</div>

        <!-- 测试页面 -->
        <div id="test-page">
            <div class="question" id="question">加载中...</div>
            <div class="options" id="options"></div>
            <button class="btn" id="next-btn" disabled>下一题</button>
        </div>

        <!-- 加载中 -->
        <div class="loading" id="loading">正在解析你的人格...</div>

        <!-- 结果页面 -->
        <div id="result-page">
            <h2 class="personality-type" id="personality-type">ISTJ</h2>
            <p class="personality-name" id="personality-name">物流师人格 | 沉稳务实，细致严谨</p>
            <div class="dimension">
                <span>精力来源</span>
                <span id="ei-dimension">内向 (I) / 外向 (E)</span>
            </div>
            <div class="dimension">
                <span>认知方式</span>
                <span id="sn-dimension">感觉 (S) / 直觉 (N)</span>
            </div>
            <div class="dimension">
                <span>决策方式</span>
                <span id="tf-dimension">思考 (T) / 情感 (F)</span>
            </div>
            <div class="dimension">
                <span>生活方式</span>
                <span id="jp-dimension">判断 (J) / 感知 (P)</span>
            </div>
            <div class="result-desc" id="result-desc">
                你的人格自带星云紫微的沉稳气场，务实、严谨、有责任心，擅长规划和执行，做事靠谱有条理，不喜欢浮躁和敷衍。你对细节敏感，注重实际，善于将复杂的事情拆解成可落地的步骤，是身边人信赖的“定心丸”。在人际关系中，你不善言辞但真诚待人，重视长期稳定的联结，做事有始有终，自带一种低调而强大的力量。
            </div>
            <button class="btn restart-btn" id="restart-btn">重新测试</button>
        </div>
    </div>

    <script>
        // 测试题目（28题，4个维度各7题）
        const questions = [
            // E/I 维度（外向/内向）
            {
                question: "1. 当你感到疲惫时，更倾向于哪种方式恢复精力？",
                options: [
                    { text: "和朋友聚会、聊天，享受热闹氛围", score: { ei: "E" } },
                    { text: "独处休息、看书或发呆，远离喧嚣", score: { ei: "I" } }
                ]
            },
            {
                question: "2. 你更在意的是？",
                options: [
                    { text: "外界的反馈和他人的看法", score: { ei: "E" } },
                    { text: "自己的内心感受和真实想法", score: { ei: "I" } }
                ]
            },
            {
                question: "3. 参加社交活动后，你通常会觉得？",
                options: [
                    { text: "精力充沛，很享受和人互动的过程", score: { ei: "E" } },
                    { text: "身心俱疲，需要独处来恢复精力", score: { ei: "I" } }
                ]
            },
            {
                question: "4. 你更擅长哪种沟通方式？",
                options: [
                    { text: "面对面交流，即时表达自己的观点", score: { ei: "E" } },
                    { text: "文字沟通，有时间思考后再表达", score: { ei: "I" } }
                ]
            },
            {
                question: "5. 当有新的社交机会时，你会？",
                options: [
                    { text: "主动参与，乐于认识新的人", score: { ei: "E" } },
                    { text: "犹豫再三，更愿意和熟悉的人相处", score: { ei: "I" } }
                ]
            },
            {
                question: "6. 你在团队中更倾向于？",
                options: [
                    { text: "主动发言，带动团队氛围", score: { ei: "E" } },
                    { text: "默默倾听，在合适的时候给出建议", score: { ei: "I" } }
                ]
            },
            {
                question: "7. 空闲时间，你更愿意？",
                options: [
                    { text: "约上朋友逛街、看电影，丰富社交", score: { ei: "E" } },
                    { text: "宅在家，做自己喜欢的事（看书、追剧等）", score: { ei: "I" } }
                ]
            },
            // S/N 维度（感觉/直觉）
            {
                question: "8. 你看待事物更关注？",
                options: [
                    { text: "眼前的事实、具体的细节", score: { sn: "S" } },
                    { text: "未来的可能性、抽象的想法", score: { sn: "N" } }
                ]
            },
            {
                question: "9. 学习新东西时，你更擅长？",
                options: [
                    { text: "通过实践、动手操作掌握", score: { sn: "S" } },
                    { text: "通过思考、联想和理论推导掌握", score: { sn: "N" } }
                ]
            },
            {
                question: "10. 当别人和你分享事情时，你更在意？",
                options: [
                    { text: "事情的来龙去脉、具体细节", score: { sn: "S" } },
                    { text: "事情背后的意义、隐藏的想法", score: { sn: "N" } }
                ]
            },
            {
                question: "11. 你对未来的态度是？",
                options: [
                    { text: "脚踏实地，做好当下的事", score: { sn: "S" } },
                    { text: "充满期待，经常畅想未来的可能性", score: { sn: "N" } }
                ]
            },
            {
                question: "12. 你更喜欢哪种类型的书籍/内容？",
                options: [
                    { text: "纪实、实用、有具体方法的内容", score: { sn: "S" } },
                    { text: "科幻、哲学、有想象力的内容", score: { sn: "N" } }
                ]
            },
            {
                question: "13. 解决问题时，你更依赖？",
                options: [
                    { text: "过往的经验和已知的事实", score: { sn: "S" } },
                    { text: "新的思路和创新的方法", score: { sn: "N" } }
                ]
            },
            {
                question: "14. 你观察事物时，更注重？",
                options: [
                    { text: "事物的表面特征、具体表现", score: { sn: "S" } },
                    { text: "事物的内在联系、潜在规律", score: { sn: "N" } }
                ]
            },
            // T/F 维度（思考/情感）
            {
                question: "15. 做决策时，你更看重？",
                options: [
                    { text: "逻辑、道理和客观事实", score: { tf: "T" } },
                    { text: "情感、人际关系和他人感受", score: { tf: "F" } }
                ]
            },
            {
                question: "16. 当朋友遇到困难时，你会？",
                options: [
                    { text: "帮他分析问题，给出解决方案", score: { tf: "T" } },
                    { text: "耐心倾听，给予情感上的安慰", score: { tf: "F" } }
                ]
            },
            {
                question: "17. 你认为“公平”的核心是？",
                options: [
                    { text: "一视同仁，按规则办事", score: { tf: "T" } },
                    { text: "因人而异，照顾到每个人的感受", score: { tf: "F" } }
                ]
            },
            {
                question: "18. 当工作/学习中出现分歧时，你会？",
                options: [
                    { text: "坚持自己的观点，用逻辑说服对方", score: { tf: "T" } },
                    { text: "尽量妥协，避免伤害彼此的关系", score: { tf: "F" } }
                ]
            },
            {
                question: "19. 你评价一个人的时候，更看重？",
                options: [
                    { text: "能力、效率和做事的结果", score: { tf: "T" } },
                    { text: "人品、善良和待人的态度", score: { tf: "F" } }
                ]
            },
            {
                question: "20. 当你犯错时，你更倾向于？",
                options: [
                    { text: "正视错误，分析原因并改正", score: { tf: "T" } },
                    { text: "在意别人的看法，容易感到自责", score: { tf: "F" } }
                ]
            },
            {
                question: "21. 你更擅长处理哪种问题？",
                options: [
                    { text: "理性的、有明确答案的问题", score: { tf: "T" } },
                    { text: "感性的、涉及人际关系的问题", score: { tf: "F" } }
                ]
            },
            // J/P 维度（判断/感知）
            {
                question: "22. 你更倾向于哪种生活方式？",
                options: [
                    { text: "有计划、有规律，提前安排好一切", score: { jp: "J" } },
                    { text: "顺其自然、灵活随性，不喜欢被束缚", score: { jp: "P" } }
                ]
            },
            {
                question: "23. 面对截止日期，你会？",
                options: [
                    { text: "提前完成，避免临时抱佛脚", score: { jp: "J" } },
                    { text: "临近截止日期再动手，效率更高", score: { jp: "P" } }
                ]
            },
            {
                question: "24. 你对“变化”的态度是？",
                options: [
                    { text: "不太喜欢，更愿意保持稳定和有序", score: { jp: "J" } },
                    { text: "乐于接受，觉得变化能带来新体验", score: { jp: "P" } }
                ]
            },
            {
                question: "25. 你在做事时，更注重？",
                options: [
                    { text: "结果，尽快完成任务", score: { jp: "J" } },
                    { text: "过程，享受做事的乐趣", score: { jp: "P" } }
                ]
            },
            {
                question: "26. 当计划被打乱时，你会？",
                options: [
                    { text: "感到焦虑，尽快调整回原计划", score: { jp: "J" } },
                    { text: "坦然接受，随机应变", score: { jp: "P" } }
                ]
            },
            {
                question: "27. 你更擅长哪种工作模式？",
                options: [
                    { text: "按部就班，遵循既定流程", score: { jp: "J" } },
                    { text: "灵活变通，根据情况调整方法", score: { jp: "P" } }
                ]
            },
            {
                question: "28. 你在整理物品时，更倾向于？",
                options: [
                    { text: "分类整理，保持整齐有序", score: { jp: "J" } },
                    { text: "随意摆放，只要自己能找到就行", score: { jp: "P" } }
                ]
            }
        ];

        // 16型人格解析（贴合星云紫微调性）
        const personalityTypes = {
            ISTJ: {
                name: "物流师人格 | 沉稳务实，细致严谨",
                desc: "你的人格自带星云紫微的沉稳气场，务实、严谨、有责任心，擅长规划和执行，做事靠谱有条理，不喜欢浮躁和敷衍。你对细节敏感，注重实际，善于将复杂的事情拆解成可落地的步骤，是身边人信赖的“定心丸”。在人际关系中，你不善言辞但真诚待人，重视长期稳定的联结，做事有始有终，自带一种低调而强大的力量。"
            },
            ISFJ: {
                name: "守卫者人格 | 温柔善良，乐于奉献",
                desc: "你是星云紫微中最温暖的存在，温柔、善良、有同理心，擅长照顾他人、包容他人，始终把身边人的感受放在心上。你务实细心，重视责任和承诺，愿意为了自己在乎的人默默付出，不追求回报。你不喜欢冲突，擅长化解矛盾，是人际关系中的“润滑剂”，自带治愈气场，总能给身边人带来安全感和温暖。"
            },
            INFJ: {
                name: "提倡者人格 | 通透睿智，心怀善意",
                desc: "你是星云紫微中最通透的灵魂，睿智、敏锐、有洞察力，善于捕捉事物的本质和人心的真实需求。你心怀善意，有自己的原则和追求，不随波逐流，始终坚持做自己认为正确的事情。你内向而深沉，不善张扬，但内心有强大的力量，擅长引导他人成长，是身边人的“心灵导师”，自带一种温润而有力量的气场。"
            },
            INTJ: {
                name: "建筑师人格 | 理性睿智，运筹帷幄",
                desc: "你是星云紫微中最具谋略的存在，理性、冷静、有远见，擅长规划未来、解决复杂问题，自带运筹帷幄的气场。你思维缜密，逻辑清晰，不被情感左右，总能做出最理智的决策。你追求完美，对自己和他人要求较高，善于创新和突破，是天生的领导者和规划者，总能在混乱中找到方向，带领身边人走向目标。"
            },
            ISTP: {
                name: "手艺人人格 | 灵活果敢，务实高效",
                desc: "你是星云紫微中最灵活的实干家，果敢、务实、动手能力强，擅长在实践中解决问题，不喜欢空谈理论。你性格随和，不喜欢被束缚，追求自由和自在，总能在突发情况中随机应变，找到最优解决方案。你低调内敛，不擅长表达，但做事高效靠谱，自带一种“万事皆可搞定”的从容气场。"
            },
            ISFP: {
                name: "艺术家人格 | 敏感细腻，热爱生活",
                desc: "你是星云紫微中最具灵气的存在，敏感、细腻、有创造力，擅长发现生活中的美好，热爱当下的每一刻。你温柔内敛，不喜欢张扬，追求内心的平静和舒适，不被外界的评价所困扰。你善于用自己的方式表达情感，无论是文字、艺术还是行动，都能传递出温暖和治愈的力量，自带一种温柔而有灵气的气场。"
            },
            INFP: {
                name: "调停者人格 | 温柔纯粹，心怀热爱",
                desc: "你是星云紫微中最纯粹的灵魂，温柔、善良、有理想，始终坚守自己的内心，不迎合、不妥协。你敏感细腻，善于共情，能深刻感受到他人的情绪，始终保持着对生活的热爱和对美好的向往。你不擅长处理复杂的人际关系，更愿意沉浸在自己的世界里，用自己的方式守护内心的纯粹，自带一种温柔而坚定的气场。"
            },
            INTP: {
                name: "逻辑学家人格 | 理性思辨，追求真理",
                desc: "你是星云紫微中最具思辨力的存在，理性、冷静、爱思考，擅长探索事物的本质和规律，对未知充满好奇。你思维敏捷，逻辑缜密，不迷信权威，始终坚持用理性和事实说话，追求真理和真相。你内向而深沉，不擅长社交，更愿意沉浸在自己的思维世界里，自带一种冷静而睿智的气场，总能提出独特的见解。"
            },
            ESTP: {
                name: "企业家人格 | 热情果敢，乐于冒险",
                desc: "你是星云紫微中最具活力的存在，热情、果敢、爱冒险，擅长把握机会，喜欢挑战新鲜事物，不畏惧困难和挫折。你外向开朗，善于社交，能快速融入各种环境，自带感染力，总能带动身边人的氛围。你务实高效，不喜欢拖泥带水，擅长在实践中积累经验，是天生的行动派，自带一种热情而有力量的气场。"
            },
            ESFP: {
                name: "表演者人格 | 热情活泼，热爱热闹",
                desc: "你是星云紫微中最耀眼的存在，热情、活泼、爱热闹，擅长表达自己，喜欢成为人群的焦点，自带感染力。你乐观开朗，不喜欢负面情绪，总能用积极的心态面对生活中的一切，善于发现生活中的乐趣。你善于社交，能快速和他人建立联系，是人际关系中的“开心果”，自带一种阳光而温暖的气场，总能给身边人带来快乐。"
            },
            ENFP: {
                name: "竞选者人格 | 乐观开朗，充满创意",
                desc: "你是星云紫微中最具创造力的存在，乐观、开朗、有想象力，擅长发现各种可能性，对生活充满热情和期待。你外向健谈，善于表达自己的想法，自带感染力，总能带动身边人的情绪。你不喜欢被束缚，追求自由和创新，擅长用自己的创意解决问题，是天生的梦想家，自带一种阳光而有活力的气场。"
            },
            ENTP: {
                name: "辩论家人格 | 思维敏捷，善于思辨",
                desc: "你是星云紫微中最具思辨力的行动派，思维敏捷、口才出众，擅长辩论和分析，喜欢挑战传统、提出新观点。你外向开朗，善于社交，能快速和他人建立联系，自带一种自信而有气场的气质。你不喜欢墨守成规，追求创新和突破，擅长在复杂的环境中找到解决问题的方法，是天生的辩论家和创新者。"
            },
            ESTJ: {
                name: "总经理人格 | 果断干练，责任感强",
                desc: "你是星云紫微中最具领导力的存在，果断、干练、有责任心，擅长组织和管理，能快速统筹全局，带领团队达成目标。你外向开朗，善于表达自己的观点，自带权威感，总能得到身边人的认可和信赖。你重视规则和秩序，做事有条理、高效靠谱，不喜欢拖延和敷衍，是天生的领导者，自带一种沉稳而有力量的气场。"
            },
            ESFJ: {
                name: "执政官人格 | 热情大方，善于社交",
                desc: "你是星云紫微中最擅长社交的存在，热情、大方、有同理心，擅长照顾他人、维护人际关系，始终把身边人的感受放在心上。你外向开朗，善于表达自己的善意，能快速和他人建立联系，是人际关系中的“粘合剂”。你重视责任和承诺，愿意为了团队和身边人付出，自带一种温暖而有亲和力的气场，总能赢得他人的喜爱。"
            },
            ENFJ: {
                name: "教育家人格 | 温暖睿智，善于引导",
                desc: "你是星云紫微中最具感染力的存在，温暖、睿智、有同理心，擅长引导他人成长，始终心怀善意和责任感。你外向开朗，善于表达自己的想法，自带感染力，总能带动身边人的情绪，激发他人的潜力。你重视人际关系，善于化解矛盾，是天生的教育家和领导者，自带一种温润而有力量的气场，总能给身边人带来希望和方向。"
            },
            ENTJ: {
                name: "指挥官人格 | 果断霸气，运筹帷幄",
                desc: "你是星云紫微中最具气场的领导者，果断、霸气、有远见，擅长规划未来、统筹全局，总能在复杂的环境中找到最优解决方案。你理性冷静，不被情感左右，善于做出正确的决策，带领团队突破困境、达成目标。你自信而强大，不畏惧挑战，擅长创新和突破，自带一种霸气而有权威的气场，总能得到身边人的追随和信赖。"
            }
        };

        // 全局变量
        let currentQuestionIndex = 0;
        const scores = { ei: [], sn: [], tf: [], jp: [] };
        let selectedOption = null;

        // DOM 元素
        const questionEl = document.getElementById("question");
        const optionsEl = document.getElementById("options");
        const nextBtn = document.getElementById("next-btn");
        const stepIndicator = document.getElementById("step-indicator");
        const testPage = document.getElementById("test-page");
        const loadingPage = document.getElementById("loading");
        const resultPage = document.getElementById("result-page");
        const personalityTypeEl = document.getElementById("personality-type");
        const personalityNameEl = document.getElementById("personality-name");
        const resultDescEl = document.getElementById("result-desc");
        const eiDimensionEl = document.getElementById("ei-dimension");
        const snDimensionEl = document.getElementById("sn-dimension");
        const tfDimensionEl = document.getElementById("tf-dimension");
        const jpDimensionEl = document.getElementById("jp-dimension");
        const restartBtn = document.getElementById("restart-btn");

        // 渲染当前题目
        function renderCurrentQuestion() {
            const question = questions[currentQuestionIndex];
            questionEl.textContent = question.question;
            optionsEl.innerHTML = "";
            selectedOption = null;
            nextBtn.disabled = true;

            question.options.forEach((option, index) => {
                const optionEl = document.createElement("div");
                optionEl.className = "option";
                optionEl.textContent = option.text;
                optionEl.dataset.index = index;
                optionEl.addEventListener("click", () => selectOption(optionEl, option));
                optionsEl.appendChild(optionEl);
            });

            // 更新步骤提示
            stepIndicator.textContent = `第${currentQuestionIndex + 1}题 / 共${questions.length}题`;
        }

        // 选择选项
        function selectOption(optionEl, option) {
            // 移除其他选项的选中状态
            document.querySelectorAll(".option").forEach(el => el.classList.remove("selected"));
            // 添加当前选项的选中状态
            optionEl.classList.add("selected");
            selectedOption = option;
            nextBtn.disabled = false;
        }

        // 计算测试结果
        function calculateResult() {
            // 统计各维度得分
            const eiScore = scores.ei.reduce((acc, val) => acc + (val === "E" ? 1 : 0), 0);
            const snScore = scores.sn.reduce((acc, val) => acc + (val === "S" ? 1 : 0), 0);
            const tfScore = scores.tf.reduce((acc, val) => acc + (val === "T" ? 1 : 0), 0);
            const jpScore = scores.jp.reduce((acc, val) => acc + (val === "J" ? 1 : 0), 0);

            // 确定各维度类型
            const eiType = eiScore >= 4 ? "E" : "I";
            const snType = snScore >= 4 ? "S" : "N";
            const tfType = tfScore >= 4 ? "T" : "F";
            const jpType = jpScore >= 4 ? "J" : "P";

            // 组合人格类型
            const personalityType = eiType + snType + tfType + jpType;
            return personalityType;
        }

        // 渲染结果页面
        function renderResult() {
            const personalityType = calculateResult();
            const personality = personalityTypes[personalityType];

            // 更新维度显示
            const eiType = personalityType[0];
            const snType = personalityType[1];
            const tfType = personalityType[2];
            const jpType = personalityType[3];

            eiDimensionEl.textContent = `${eiType === "E" ? "外向 (E)" : "内向 (I)"}`;
            snDimensionEl.textContent = `${snType === "S" ? "感觉 (S)" : "直觉 (N)"}`;
            tfDimensionEl.textContent = `${tfType === "T" ? "思考 (T)" : "情感 (F)"}`;
            jpDimensionEl.textContent = `${jpType === "J" ? "判断 (J)" : "感知 (P)"}`;

            // 更新人格信息
            personalityTypeEl.textContent = personalityType;
            personalityNameEl.textContent = personality.name;
            resultDescEl.textContent = personality.desc;

            // 切换页面
            loadingPage.style.display = "none";
            resultPage.style.display = "block";
        }

        // 下一题按钮点击事件
        nextBtn.addEventListener("click", () => {
            // 记录当前选项得分
            const { ei, sn, tf, jp } = selectedOption.score;
            if (ei) scores.ei.push(ei);
            if (sn) scores.sn.push(sn);
            if (tf) scores.tf.push(tf);
            if (jp) scores.jp.push(jp);

            // 切换到下一题或结果页
            currentQuestionIndex++;
            if (currentQuestionIndex < questions.length) {
                renderCurrentQuestion();
            } else {
                // 显示加载页，延迟渲染结果（提升体验）
                testPage.style.display = "none";
                loadingPage.style.display = "block";
                setTimeout(renderResult, 1000);
            }
        });

        // 重新测试按钮点击事件
        restartBtn.addEventListener("click", () => {
            // 重置变量
            currentQuestionIndex = 0;
            scores.ei = [];
            scores.sn = [];
            scores.tf = [];
            scores.jp = [];
            selectedOption = null;

            // 切换页面
            resultPage.style.display = "none";
            testPage.style.display = "block";
            renderCurrentQuestion();
        });

        // 初始化测试
        renderCurrentQuestion();
    </script>
</body>
</html>
