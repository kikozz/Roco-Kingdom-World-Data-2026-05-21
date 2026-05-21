# PB proto_out 对比详细报告

说明：文件名、message、enum、字段名等代码标识保留原样，方便搜索。

## 删除的 Zone 服务接口中文说明（完整）

说明：下面的中文含义是根据 `message` 名、字段名和协议上下文推断出来的；如果游戏客户端另有业务层命名，最终含义以客户端逻辑为准。`Req` 表示客户端请求，`Rsp` 表示服务器响应，`Nty` 表示服务器通知。

| message | 中文含义 | 字段说明 |
|---|---|---|
| `ZoneBadgeChallengeEnterReq` | 进入徽章挑战节点请求 | 字段 1 `node_id` (`uint32`)：挑战节点 ID |
| `ZoneBadgeChallengeEnterRsp` | 进入徽章挑战节点响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneBadgeChallengeSelectUpgradeReq` | 徽章挑战选择升级项请求 | 字段 1 `index` (`repeated uint32`)：选择的升级项索引列表 |
| `ZoneBadgeChallengeSelectUpgradeRsp` | 徽章挑战选择升级项响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `upgrade_ids` (`repeated uint32`)：服务器确认或返回的升级 ID 列表 |
| `ZoneCancelTaskRedPointReq` | 取消任务红点提示请求 | 字段 1 `task_id` (`uint32`)：任务 ID |
| `ZoneCancelTaskRedPointRsp` | 取消任务红点提示响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneChangeTaskSwitchDataReq` | 修改任务开关状态请求 | 字段 1 `switch_id` (`uint32`)：任务开关 ID；字段 2 `is_open` (`uint32`)：是否开启，通常 1 表示开启、0 表示关闭 |
| `ZoneChangeTaskSwitchDataRsp` | 修改任务开关状态响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `task_switch` (`Next.PlayerTaskSwitchData`)：玩家任务开关数据 |
| `ZoneCheckColorSuitStateReq` | 检查染色套装状态请求 | 字段 1 `fashion_bond_id` (`int32`)：时装羁绊或套装关联 ID |
| `ZoneCheckColorSuitStateRsp` | 检查染色套装状态响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `color_suit_state` (`dataconfig.FashionBondColorSuitState`)：染色套装状态 |
| `ZoneClearDungeonReq` | 清理或结算副本请求 | 字段 1 `dungeon_cfg_id` (`int32`)：副本配置 ID |
| `ZoneClearDungeonRsp` | 清理或结算副本响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneFeedVideoDelUploadFileReq` | 删除已上传视频文件请求 | 字段 1 `file_name` (`string`)：文件名 |
| `ZoneFeedVideoDelUploadFileRsp` | 删除已上传视频文件响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `video_upload_info` (`Next.FeedVideoUploadInfo`)：视频上传状态或上传信息 |
| `ZoneFeedVideoFeedbackReq` | 视频动态评论或反馈请求 | 字段 1 `uin` (`uint32`)：玩家账号 ID；字段 2 `feed_id` (`uint64`)：动态或视频内容 ID；字段 3 `comment_content` (`string`)：评论或反馈内容 |
| `ZoneFeedVideoFeedbackRsp` | 视频动态评论或反馈响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `feed` (`Next.ZoneMagicFeedInfo`)：动态内容信息；字段 3 `ban_info` (`Next.BanInfo`)：禁言或处罚信息；字段 4 `comment_info` (`Next.FeedCommentInfo`)：评论结果信息 |
| `ZoneGetAppearanceInfoReq` | 获取玩家外观信息请求 | 无字段。 |
| `ZoneGetAppearanceInfoRsp` | 获取玩家外观信息响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `appearance_info` (`Next.PlayerAppearanceInfo`)：玩家外观数据 |
| `ZoneGetCampFruitNpcInfosReq` | 获取营地果树相关 NPC 信息请求 | 字段 1 `camp_content_ids` (`repeated int32`)：营地内容 ID 列表 |
| `ZoneGetCampFruitNpcInfosRsp` | 获取营地果树相关 NPC 信息响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `camp_fruit_npc_infos` (`repeated Next.CampFruitNpcInfo`)：营地果树 NPC 信息列表 |
| `ZoneGetClaimableGlassTintReq` | 获取可领取的玻璃或镜片染色请求 | 字段 1 `fashion_bond_id` (`int32`)：时装羁绊或套装关联 ID；字段 2 `is_shining` (`bool`)：是否闪光或闪耀状态 |
| `ZoneGetClaimableGlassTintRsp` | 获取可领取的玻璃或镜片染色响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 3 `claimable_glass` (`repeated Next.GlassInfo`)：可领取的玻璃或镜片染色信息列表 |
| `ZoneGetHandbookStatReq` | 获取图鉴统计请求 | 字段 1 `page` (`uint32`)：请求页码；字段 2 `version` (`int64`)：数据版本号 |
| `ZoneGetHandbookStatRsp` | 获取图鉴统计响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `hb_coll` (`repeated Next.HandbookRecordCollection`)：图鉴记录集合；字段 3 `total_page` (`uint32`)：总页数；字段 4 `req_page` (`uint32`)：本次返回的页码；字段 5 `page_cap` (`uint32`)：每页容量；字段 6 `version` (`int64`)：数据版本号 |
| `ZoneGetSubTaskTokenTriggeredTaskInfoReq` | 获取子任务 token 触发任务信息请求 | 无字段。 |
| `ZoneGetSubTaskTokenTriggeredTaskInfoRsp` | 获取子任务 token 触发任务信息响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `sub_task_token_triggered_task_info` (`repeated Next.PlayerSubTaskInfo_SubTaskTokenTriggeredTaskInfo`)：子任务 token 触发任务信息列表 |
| `ZoneGetTaskSwitchDataReq` | 获取任务开关数据请求 | 无字段。 |
| `ZoneGetTaskSwitchDataRsp` | 获取任务开关数据响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `task_switch` (`Next.PlayerTaskSwitchData`)：玩家任务开关数据 |
| `ZoneHeartbeatReq` | Zone 服务器心跳请求 | 无字段。 |
| `ZoneHeartbeatRsp` | Zone 服务器心跳响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `svr_time` (`uint64`)：服务器当前时间戳 |
| `ZoneHomePetFoodCompoundReq` | 家园宠物食物合成请求 | 字段 1 `food_cfg_id` (`int32`)：食物配置 ID；字段 2 `food_num` (`int32`)：食物数量或合成数量；字段 3 `cost_item_cfg_id` (`repeated int32`)：消耗道具配置 ID 列表 |
| `ZoneHomePetFoodCompoundRsp` | 家园宠物食物合成响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneJudgePayReq` | 支付判定请求 | 字段 1 `openid` (`string`)：支付账号 openid；字段 2 `pay_amount` (`uint32`)：支付金额 |
| `ZoneJudgePayRsp` | 支付判定响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `instruction` (`Next.HopeInstruction`)：支付指令或引导信息 |
| `ZoneLogoutReq` | 登出请求 | 字段 1 `uin` (`uint32`)：玩家账号 ID；字段 2 `dev_info` (`Next.ClientDevInfo`)：客户端设备信息；字段 3 `is_notify_cli` (`bool`)：是否通知客户端 |
| `ZoneLogoutRsp` | 登出响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneModifyBagListSortReq` | 修改背包列表排序请求 | 字段 1 `item_type` (`dataconfig.BagItemType`)：背包道具类型；字段 2 `sort_type` (`dataconfig.Sequence`)：排序方式 |
| `ZoneModifyBagListSortRsp` | 修改背包列表排序响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZonePetBasePointAssignReq` | 宠物基础点数分配请求 | 字段 1 `base_point_info` (`repeated Next.ZonePetBasePointAssignReq.BasePointInfo`)：基础点数分配项列表；字段 2 `pet_gid` (`uint32`)：宠物全局 ID |
| `ZonePetBasePointAssignReq.BasePointInfo` | 宠物基础点数分配项 | 字段 1 `attribute_type` (`dataconfig.AttributeType`)：属性类型；字段 2 `add_num` (`int32`)：增加点数 |
| `ZonePetBasePointAssignRsp` | 宠物基础点数分配响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZonePetDeleteReq` | 删除或放生宠物请求 | 字段 1 `gid` (`uint32`)：宠物或对象全局 ID |
| `ZonePetDeleteRsp` | 删除或放生宠物响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZonePetSetFollowReq` | 设置跟随宠物请求 | 字段 1 `gid` (`uint32`)：宠物或对象全局 ID |
| `ZonePetSetFollowRsp` | 设置跟随宠物响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `gid` (`uint32`)：宠物或对象全局 ID |
| `ZonePetUseBagItemReq` | 对宠物使用背包道具请求 | 字段 1 `pet_gid` (`uint32`)：宠物全局 ID；字段 2 `bag_item_info` (`repeated Next.ZonePetUseBagItemReq.BagItemInfo`)：使用的背包道具列表；字段 3 `pet_train_type` (`dataconfig.PetTrainType`)：宠物培养类型 |
| `ZonePetUseBagItemReq.BagItemInfo` | 对宠物使用的道具项 | 字段 1 `id` (`uint32`)：道具 ID；字段 2 `num` (`uint32`)：数量 |
| `ZonePetUseBagItemRsp` | 对宠物使用背包道具响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZonePublishVideoToWechatReq` | 发布视频到微信请求 | 字段 1 `video_file_id` (`string`)：视频文件 ID |
| `ZonePublishVideoToWechatRsp` | 发布视频到微信响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneQueryAdventureChapterReq` | 查询冒险章节请求 | 无字段。 |
| `ZoneQueryAdventureChapterRsp` | 查询冒险章节响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `chapter_id` (`uint32`)：章节 ID；字段 3 `rewarded` (`bool`)：是否已领取奖励；字段 4 `region_id` (`uint32`)：区域 ID |
| `ZoneQuerySceneTaskStatReq` | 查询场景任务状态请求 | 字段 1 `uin` (`uint32`)：玩家账号 ID |
| `ZoneQuerySceneTaskStatRsp` | 查询场景任务状态响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `scene_state_data` (`Next.TaskScenesvrStateData`)：场景任务状态数据 |
| `ZoneRefreshBadgeChallengeCardReq` | 刷新徽章挑战卡牌请求 | 无字段。 |
| `ZoneRefreshBadgeChallengeCardRsp` | 刷新徽章挑战卡牌响应 | 字段 1 `event_infos` (`repeated Next.ChallengeEventCardInfo`)：挑战事件卡牌信息列表；字段 2 `remain_coin` (`uint32`)：剩余代币数量；字段 3 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 4 `refresh_need_coin` (`uint32`)：刷新所需代币数量；字段 5 `pet_unit_type` (`repeated uint32`)：宠物单位类型列表 |
| `ZoneSceneApplyVisitConfirmReq` | 确认场景访问申请请求 | 字段 1 `apply_uin` (`uint32`)：申请人账号 ID；字段 2 `agree` (`bool`)：是否同意申请；字段 3 `pos` (`Next.Position`)：位置坐标 |
| `ZoneSceneApplyVisitConfirmRsp` | 确认场景访问申请响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSceneApplyVisitListQueryReq` | 查询场景访问申请列表请求 | 无字段。 |
| `ZoneSceneApplyVisitListQueryRsp` | 查询场景访问申请列表响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `apply_list` (`repeated Next.ZoneSceneApplyVisitListQueryRsp.ApplyInfo`)：访问申请列表 |
| `ZoneSceneApplyVisitListQueryRsp.ApplyInfo` | 场景访问申请人信息 | 字段 1 `icon` (`uint32`)：头像或图标 ID；字段 2 `level` (`uint32`)：等级；字段 3 `name` (`bytes`)：名称；字段 4 `uin` (`uint32`)：玩家账号 ID；字段 5 `apply_time` (`uint32`)：申请时间；字段 6 `card_info` (`Next.PlayerCardBriefInfo`)：玩家名片简要信息 |
| `ZoneSceneApplyVisitReq` | 申请访问其他玩家场景请求 | 字段 1 `visit_uin` (`uint32`)：被访问玩家账号 ID |
| `ZoneSceneApplyVisitRsp` | 申请访问其他玩家场景响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `extra_data` (`uint32`)：额外数据 |
| `ZoneSceneCastSceneSkillReq` | 施放场景技能请求 | 字段 1 `time_stamp` (`uint32`)：时间戳；字段 2 `skill_id` (`int32`)：技能 ID；字段 3 `skill_status_type` (`int32`)：技能状态类型；字段 4 `is_add_status` (`bool`)：是否添加状态 |
| `ZoneSceneCastSceneSkillRsp` | 施放场景技能响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSceneChangeMoveModeReq` | 切换场景移动模式请求 | 字段 1 `move_id` (`int32`)：移动模式 ID；字段 2 `stamina` (`int32`)：体力值；字段 3 `need_start_cost` (`int32`)：是否需要开始消耗体力 |
| `ZoneSceneChangeMoveModeRsp` | 切换场景移动模式响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `server_stamina` (`int32`)：服务器校正后的体力值；字段 3 `server_move_id` (`int32`)：服务器校正后的移动模式 ID |
| `ZoneSceneGeneralOpReq` | 场景通用操作请求 | 字段 1 `op_type` (`uint32`)：操作类型；字段 2 `param_list` (`repeated uint64`)：参数列表 |
| `ZoneSceneGeneralOpRsp` | 场景通用操作响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSceneNpcBattleSeriesReq` | 触发 NPC 连续战斗请求 | 字段 1 `npc_id_list` (`repeated uint64`)：NPC 对象 ID 列表 |
| `ZoneSceneNpcBattleSeriesRsp` | 触发 NPC 连续战斗响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSceneSetAvatarPosReq` | 设置角色场景位置请求 | 字段 1 `pos` (`Next.Point`)：位置坐标；字段 2 `reason` (`uint32`)：原因 |
| `ZoneSceneSetAvatarPosRsp` | 设置角色场景位置响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSceneStrongStormNty` | 场景强风暴状态通知 | 字段 1 `enter` (`bool`)：是否进入强风暴状态 |
| `ZoneSceneThrowCollisionReq` | 场景投掷物碰撞请求 | 字段 1 `throw_type` (`Next.ThrowType`)：投掷类型；字段 2 `gid` (`int32`)：宠物或对象全局 ID；字段 3 `throw_id` (`int32`)：投掷物 ID；字段 4 `collision_pos` (`Next.Position`)：碰撞位置；字段 5 `fly_distance` (`int32`)：飞行距离；字段 6 `item_conf_id` (`int32`)：道具配置 ID |
| `ZoneSceneThrowCollisionRsp` | 场景投掷物碰撞响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `is_broken` (`bool`)：投掷物是否破碎；字段 3 `throw_power` (`int32`)：投掷力度 |
| `ZoneSceneWorldCombatHitReq` | 大世界战斗命中请求 | 字段 1 `victim_id` (`uint64`)：受击目标对象 ID；字段 2 `hit_info` (`Next.WorldCombatHitInfo`)：命中信息 |
| `ZoneSceneWorldCombatHitRsp` | 大世界战斗命中响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSceneWorldCombatSkillBuffReq` | 大世界战斗技能 Buff 请求 | 字段 1 `npc_id` (`uint64`)：NPC 对象 ID；字段 2 `skill_buff_info` (`Next.WorldCombatSkillBuffInfo`)：技能 Buff 信息 |
| `ZoneSceneWorldCombatSkillBuffRsp` | 大世界战斗技能 Buff 响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSceneWorldCombatSkillCastReq` | 大世界战斗施放技能请求 | 字段 1 `npc_id` (`uint64`)：NPC 对象 ID；字段 2 `skill_info` (`Next.WorldCombatSkillCastInfo`)：技能信息 |
| `ZoneSceneWorldCombatSkillCastRsp` | 大世界战斗施放技能响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSceneWorldCombatSkillEndReq` | 大世界战斗技能结束请求 | 字段 1 `npc_id` (`uint64`)：NPC 对象 ID；字段 2 `skill_end_info` (`Next.WorldCombatSkillEndInfo`)：技能结束信息 |
| `ZoneSceneWorldCombatSkillEndRsp` | 大世界战斗技能结束响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSceneWorldCombatSkillFireBulletReq` | 大世界战斗技能发射子弹请求 | 字段 1 `npc_id` (`uint64`)：NPC 对象 ID；字段 2 `skill_fire_bullet_info` (`Next.WorldCombatSkillFireBulletInfo`)：技能发射子弹信息 |
| `ZoneSceneWorldCombatSkillFireBulletRsp` | 大世界战斗技能发射子弹响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSceneWorldCombatSkillJumpEndReq` | 大世界战斗技能跳跃结束请求 | 字段 1 `npc_id` (`uint64`)：NPC 对象 ID；字段 2 `skill_jump_end_info` (`Next.WorldCombatSkillJumpEndInfo`)：技能跳跃结束信息 |
| `ZoneSceneWorldCombatSkillJumpEndRsp` | 大世界战斗技能跳跃结束响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSceneWorldCombatSkillJumpReq` | 大世界战斗技能跳跃请求 | 字段 1 `npc_id` (`uint64`)：NPC 对象 ID；字段 2 `skill_jump_info` (`Next.WorldCombatSkillJumpInfo`)：技能跳跃信息 |
| `ZoneSceneWorldCombatSkillJumpRsp` | 大世界战斗技能跳跃响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSceneWorldCombatSkillPetCollisionReq` | 大世界战斗技能宠物碰撞请求 | 字段 1 `npc_id` (`uint64`)：NPC 对象 ID；字段 2 `skill_pet_collision` (`Next.WorldCombatSkillPetCollisionInfo`)：技能宠物碰撞信息 |
| `ZoneSceneWorldCombatSkillPetCollisionRsp` | 大世界战斗技能宠物碰撞响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSceneWorldCombatSkillRcdReq` | 大世界战斗 RCD 技能请求 | 字段 1 `npc_id` (`uint64`)：NPC 对象 ID；字段 2 `skill_rcd_info` (`Next.WorldCombatSkillRcdInfo`)：RCD 技能信息 |
| `ZoneSceneWorldCombatSkillRcdRsp` | 大世界战斗 RCD 技能响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSceneWorldCombatSkillSpawnBulletReq` | 大世界战斗技能生成子弹请求 | 字段 1 `npc_id` (`uint64`)：NPC 对象 ID；字段 2 `skill_spawn_bullet_info` (`Next.WorldCombatSkillSpawnBulletInfo`)：技能生成子弹信息 |
| `ZoneSceneWorldCombatSkillSpawnBulletRsp` | 大世界战斗技能生成子弹响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSceneWorldCombatSkillSpawnNpcReq` | 大世界战斗技能生成 NPC 请求 | 字段 1 `npc_id` (`uint64`)：NPC 对象 ID；字段 2 `skill_spawn_npc_info` (`Next.WorldCombatSkillSpawnNpcInfo`)：技能生成 NPC 信息 |
| `ZoneSceneWorldCombatSkillSpawnNpcRsp` | 大世界战斗技能生成 NPC 响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSecondaryPasswordActionCheckReq` | 二级密码行为校验请求 | 字段 1 `action` (`int32`)：二级密码校验的行为类型 |
| `ZoneSecondaryPasswordActionCheckRsp` | 二级密码行为校验响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSecondaryPasswordCancelFreeReq` | 取消二级密码免验证请求 | 无字段。 |
| `ZoneSecondaryPasswordCancelFreeRsp` | 取消二级密码免验证响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneSyncTempReq` | 同步温度请求 | 字段 1 `world_temp` (`uint32`)：世界温度；字段 2 `field_temp` (`int32`)：场景或区域温度 |
| `ZoneSyncTempRsp` | 同步温度响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `body_temp_final_val` (`int32`)：最终体感温度值；字段 3 `reach_final_time` (`uint32`)：达到最终温度的时间 |
| `ZoneTaskTraceReq` | 任务追踪设置请求 | 字段 1 `task_id` (`uint32`)：任务 ID；字段 2 `use_trace` (`uint32`)：是否开启任务追踪 |
| `ZoneTaskTraceRsp` | 任务追踪设置响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `task_info_list` (`repeated Next.PlayerTaskInfo`)：任务信息列表 |
| `ZoneTlogReportReq` | TLog 日志上报请求 | 字段 1 `tlog_tag` (`string`)：TLog 标签；字段 2 `tlog_content` (`string`)：TLog 内容 |
| `ZoneTlogReportRsp` | TLog 日志上报响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneTssMessageCheckReq` | TSS 消息安全检查请求 | 字段 1 `message` (`bytes`)：待检查的消息内容；字段 2 `message_type` (`dataconfig.TssMsgType`)：消息类型 |
| `ZoneTssMessageCheckRsp` | TSS 消息安全检查响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息 |
| `ZoneVodVideoSignatureReq` | 获取 VOD 视频上传签名请求 | 无字段。 |
| `ZoneVodVideoSignatureRsp` | 获取 VOD 视频上传签名响应 | 字段 1 `ret_info` (`Next.RetInfo`)：返回状态、错误码和错误信息；字段 2 `signature` (`string`)：上传签名；字段 3 `file_name` (`string`)：文件名 |
## 总览

- 文件：旧版 66 个 -> 新版 72 个；新增 6 个，删除 0 个，内容变化 46 个。
- `proto_out` 总行数差异：新增 3552 行 / 删除 1330 行。
- message：旧版 3298 个 -> 新版 3462 个；新增 283 个，删除 119 个，移动 67 个。
- enum：旧版 942 个 -> 新版 1007 个；新增 66 个，删除 1 个，移动 7 个。
- 共有 message 的字段变化：新增字段 263 个，删除字段 44 个，同 tag 改名或改类型 12 个。
- 共有 enum 的枚举值变化：新增枚举值 523 个，删除枚举值 150 个，同数值改名 8 个。

## 新增文件

- com_badge_trial.proto
- com_cs_rankboard.proto
- com_debug_draw.proto
- com_friend_data.proto
- com_season.proto
- world_combat.proto

## 消失文件

- 无

## 变化最大的文件

| 文件 | 状态 | 新增行 | 删除行 |
|---|---:|---:|---:|
| `zonesvr.proto` | 变化 | 671 | 522 |
| `space_data.proto` | 变化 | 278 | 358 |
| `xls_enum.proto` | 变化 | 599 | 34 |
| `world_combat.proto` | 新增 | 357 | 0 |
| `c2s_cmd.proto` | 变化 | 131 | 150 |
| `com_debug_draw.proto` | 新增 | 202 | 0 |
| `com_activity.proto` | 变化 | 173 | 1 |
| `com_badge_trial.proto` | 新增 | 160 | 0 |
| `scene_notify.proto` | 变化 | 4 | 146 |
| `space_action.proto` | 变化 | 121 | 1 |
| `errorcode.proto` | 变化 | 100 | 0 |
| `com_player.proto` | 变化 | 80 | 0 |
| `zone_gm.proto` | 变化 | 72 | 0 |
| `com_action.proto` | 变化 | 56 | 13 |
| `com_cs_rankboard.proto` | 新增 | 66 | 0 |
| `com_gm.proto` | 变化 | 17 | 47 |
| `com_pet.proto` | 变化 | 61 | 1 |
| `com_battle.proto` | 变化 | 45 | 6 |
| `com_player_data.proto` | 变化 | 48 | 0 |
| `com_friend_data.proto` | 新增 | 47 | 0 |
| `com_season.proto` | 新增 | 37 | 0 |
| `battle_data.proto` | 变化 | 36 | 0 |
| `com_battle_enum.proto` | 变化 | 35 | 0 |
| `com_account.proto` | 变化 | 25 | 1 |
| `world_map.proto` | 变化 | 0 | 23 |

## import 变化

新增 import：
- `battle_data.proto` 新增 import `com_battle_enum.proto`
- `battle_data.proto` 新增 import `com_season.proto`
- `com_action.proto` 新增 import `com_season.proto`
- `com_battle.proto` 新增 import `com_season.proto`
- `com_pet.proto` 新增 import `com_season.proto`
- `com_player.proto` 新增 import `com_badge_trial.proto`
- `friend_data.proto` 新增 import `com_friend_data.proto`
- `scene_notify.proto` 新增 import `com_debug_draw.proto`
- `space_action.proto` 新增 import `com_action.proto`
- `space_action.proto` 新增 import `com_player_data.proto`
- `space_action.proto` 新增 import `world_combat.proto`
- `space_data.proto` 新增 import `com_battle_enum.proto`
- `space_data.proto` 新增 import `com_friend_data.proto`
- `space_data.proto` 新增 import `com_season.proto`
- `space_data.proto` 新增 import `world_combat.proto`
- `zonesvr.proto` 新增 import `client.proto`
- `zonesvr.proto` 新增 import `com_badge_trial.proto`
- `zonesvr.proto` 新增 import `com_cs_rankboard.proto`
- `zonesvr.proto` 新增 import `world_combat.proto`

## 符号移动

- enum `BlockType`：`space_data.proto` -> `world_combat.proto`；含义：Block / 类型，属于枚举定义，通常表示类型枚举。
- enum `DEBUG_DRAW_CALL_TYPE`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：DEBUG / DRAW / CALL / TYPE，属于枚举定义，通常表示相关结构或枚举。
- enum `FriendSource`：`friend_data.proto` -> `com_friend_data.proto`；含义：好友 / 来源，属于枚举定义，通常表示来源枚举。
- enum `ServerDebugDrawType`：`com_gm.proto` -> `com_debug_draw.proto`；含义：Server / Debug / Draw / 类型，属于枚举定义，通常表示类型枚举。
- enum `SkillActionType`：`space_data.proto` -> `world_combat.proto`；含义：Skill / 动作 / 类型，属于枚举定义，通常表示类型枚举。
- enum `SkillHitType`：`space_data.proto` -> `world_combat.proto`；含义：Skill / Hit / 类型，属于枚举定义，通常表示类型枚举。
- enum `WorldCombatDotsSkillPosLerpSyncInfo.Type`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Pos / Lerp / 同步 / 信息 / 类型，属于枚举定义，通常表示类型枚举。
- message `ActorInfo_WorldCombatSkillAction`：`space_data.proto` -> `world_combat.proto`；含义：场景对象 / 信息 / 世界 / Combat / Skill / 动作，属于协议消息或数据结构，通常表示动作枚举或动作结构。
- message `DebugDrawBoxData`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：Debug / Draw / 盒子 / 数据，属于协议消息或数据结构，通常表示数据结构。
- message `DebugDrawCapsuleData`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：Debug / Draw / Capsule / 数据，属于协议消息或数据结构，通常表示数据结构。
- message `DebugDrawCircleData`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：Debug / Draw / Circle / 数据，属于协议消息或数据结构，通常表示数据结构。
- message `DebugDrawColor`：`com_gm.proto` -> `com_debug_draw.proto`；含义：Debug / Draw / Color，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `DebugDrawCylinderData`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：Debug / Draw / Cylinder / 数据，属于协议消息或数据结构，通常表示数据结构。
- message `DebugDrawLineData`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：Debug / Draw / Line / 数据，属于协议消息或数据结构，通常表示数据结构。
- message `DebugDrawMeshData`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：Debug / Draw / Mesh / 数据，属于协议消息或数据结构，通常表示数据结构。
- message `DebugDrawNavMeshData`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：Debug / Draw / Nav / Mesh / 数据，属于协议消息或数据结构，通常表示数据结构。
- message `DebugDrawPointData`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：Debug / Draw / Point / 数据，属于协议消息或数据结构，通常表示数据结构。
- message `DebugDrawPointSetData`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：Debug / Draw / Point / 设置 / 数据，属于协议消息或数据结构，通常表示数据结构。
- message `DebugDrawRotator`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：Debug / Draw / Rotator，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `DebugDrawSphereData`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：Debug / Draw / Sphere / 数据，属于协议消息或数据结构，通常表示数据结构。
- message `DebugDrawTextData`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：Debug / Draw / Text / 数据，属于协议消息或数据结构，通常表示数据结构。
- message `DebugDrawWireFrame`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：Debug / Draw / Wire / Frame，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `DebugDrawWireFrameData`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：Debug / Draw / Wire / Frame / 数据，属于协议消息或数据结构，通常表示数据结构。
- message `HomeAccessInfo`：`com_home.proto` -> `com_player_data.proto`；含义：Home / Access / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `HomeBanInfo`：`com_home.proto` -> `com_player_data.proto`；含义：Home / 禁用 / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `HomeViolationInfo`：`com_home.proto` -> `com_player_data.proto`；含义：Home / Violation / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `NavMeshDebugDraw`：`com_gm.proto` -> `com_debug_draw.proto`；含义：Nav / Mesh / Debug / Draw，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `NavMeshDebugDraw.NavMeshBoundary`：`com_gm.proto` -> `com_debug_draw.proto`；含义：Nav / Mesh / Debug / Draw / Nav / Mesh / Boundary，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `NavMeshDebugDraw.NavMeshPoly`：`com_gm.proto` -> `com_debug_draw.proto`；含义：Nav / Mesh / Debug / Draw / Nav / Mesh / Poly，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `NavMeshDebugDraw.NavMeshTile`：`com_gm.proto` -> `com_debug_draw.proto`；含义：Nav / Mesh / Debug / Draw / Nav / Mesh / Tile，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `SceneGmDebugDrawCall`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：场景 / Gm / Debug / Draw / Call，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `Snapshoot_WorldCombatSkillActionCrush`：`space_data.proto` -> `world_combat.proto`；含义：Snapshoot / 世界 / Combat / Skill / 动作 / Crush，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `Snapshoot_WorldCombatSkillActionJump`：`space_data.proto` -> `world_combat.proto`；含义：Snapshoot / 世界 / Combat / Skill / 动作 / Jump，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `Snapshoot_WorldCombatSkillActionMissile`：`space_data.proto` -> `world_combat.proto`；含义：Snapshoot / 世界 / Combat / Skill / 动作 / Missile，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `Snapshoot_WorldCombatSkillActionRcd`：`space_data.proto` -> `world_combat.proto`；含义：Snapshoot / 世界 / Combat / Skill / 动作 / Rcd，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `Snapshoot_WorldCombatSkillActionShowHide`：`space_data.proto` -> `world_combat.proto`；含义：Snapshoot / 世界 / Combat / Skill / 动作 / Show / Hide，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `WorldCombatDotsSkillAnimCancelInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Anim / 取消 / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillCastInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Cast / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillCrushEndInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Crush / 结束 / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillCrushInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Crush / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillEndInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / 结束 / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillHiddenEndInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Hidden / 结束 / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillHiddenInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Hidden / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillHitInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Hit / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillJumpCancelInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Jump / 取消 / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillJumpEndInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Jump / 结束 / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillJumpInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Jump / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillLookAtInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Look / At / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillMissileDestroyInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Missile / Destroy / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillMissileLaunchInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Missile / Launch / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillMissileLaunchInfo_Curve`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Missile / Launch / 信息 / Curve，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `WorldCombatDotsSkillMissileLaunchInfo_Normal`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Missile / Launch / 信息 / 普通，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `WorldCombatDotsSkillMissileLaunchInfo_Trace`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Missile / Launch / 信息 / Trace，属于协议消息或数据结构，通常表示相关结构或枚举。
- message `WorldCombatDotsSkillMissileStopTraceInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Missile / Stop / Trace / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillPosLerpSyncInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Pos / Lerp / 同步 / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillRcdEndInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Rcd / 结束 / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillRcdInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Rcd / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillRotateInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Rotate / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillSelectPosInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / 选择 / Pos / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillSelectPosInfo.SelectPosInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / 选择 / Pos / 信息 / 选择 / Pos / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillShowHideCompInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Show / Hide / 组件 / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatDotsSkillShowHideInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Dots / Skill / Show / Hide / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatHitInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Hit / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatSkillBuffInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Skill / Buff / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatSkillCastInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Skill / Cast / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatSkillEndInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Skill / 结束 / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatSkillFireBulletInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Skill / Fire / Bullet / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatSkillJumpEndInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Skill / Jump / 结束 / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatSkillJumpInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Skill / Jump / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatSkillPetCollisionInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Skill / 宠物 / Collision / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatSkillRcdInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Skill / Rcd / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatSkillSpawnBulletInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Skill / Spawn / Bullet / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `WorldCombatSkillSpawnNpcInfo`：`space_data.proto` -> `world_combat.proto`；含义：世界 / Combat / Skill / Spawn / NPC / 信息，属于协议消息或数据结构，通常表示信息结构。
- message `ZoneSceneGmDebugDrawCall`：`scene_notify.proto` -> `com_debug_draw.proto`；含义：Zone 服务 / 场景 / Gm / Debug / Draw / Call，属于协议消息或数据结构，通常表示相关结构或枚举。

## 按文件统计的新增 message

### battle_buff_data.proto
- `BuffData_146_Common`；含义：Buff / 数据 / 146 / Common，属于协议消息或数据结构，通常表示相关结构或枚举。
- `BuffData_146_PetBuffMaps`；含义：Buff / 数据 / 146 / 宠物 / Buff / Maps，属于协议消息或数据结构，通常表示相关结构或枚举。
- `BuffData_146_sks`；含义：Buff / 数据 / 146 / sks，属于协议消息或数据结构，通常表示相关结构或枚举。

### battle_data.proto
- `BattleBoxShieldBreak`；含义：战斗 / 盒子 / Shield / Break，属于协议消息或数据结构，通常表示相关结构或枚举。

### com_account.proto
- `WegameAuthResult`；含义：Wegame / Auth / 结果，属于协议消息或数据结构，通常表示相关结构或枚举。

### com_action.proto
- `CreatedRoleplayProp`；含义：Created / 角色扮演 / Prop，属于协议消息或数据结构，通常表示相关结构或枚举。
- `CreatedRoleplayPropData`；含义：Created / 角色扮演 / Prop / 数据，属于协议消息或数据结构，通常表示数据结构。
- `EnteredRoleplayPropData`；含义：Entered / 角色扮演 / Prop / 数据，属于协议消息或数据结构，通常表示数据结构。
- `ThrowStarMagicResult`；含义：Throw / Star / 魔法 / 结果，属于协议消息或数据结构，通常表示相关结构或枚举。

### com_activity.proto
- `ActivityPetTripData_CurPetTripInfo`；含义：活动 / 宠物 / 旅行 / 数据 / Cur / 宠物 / 旅行 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ActivityPetTripData_LotteryResult`；含义：活动 / 宠物 / 旅行 / 数据 / 抽奖 / 结果，属于协议消息或数据结构，通常表示相关结构或枚举。
- `ActivityPetTripData_PetTripFormationInfo`；含义：活动 / 宠物 / 旅行 / 数据 / 宠物 / 旅行 / Formation / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ActivityPetTripData_PetTripRecordInfo`；含义：活动 / 宠物 / 旅行 / 数据 / 宠物 / 旅行 / Record / 信息，属于协议消息或数据结构，通常表示信息结构。
- `PlayerActivityInfo_ActivityBaseMixData`；含义：玩家 / 活动 / 信息 / 活动 / 基础 / 混合 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `PlayerActivityInfo_ActivityBaseMixSlotData`；含义：玩家 / 活动 / 信息 / 活动 / 基础 / 混合 / Slot / 数据，属于协议消息或数据结构，通常表示数据结构。
- `PlayerActivityInfo_ActivityGlobalChallengeData`；含义：玩家 / 活动 / 信息 / 活动 / 全局 / 挑战 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `PlayerActivityInfo_ActivityGlobalChallengeData_Progress`；含义：玩家 / 活动 / 信息 / 活动 / 全局 / 挑战 / 数据 / Progress，属于协议消息或数据结构，通常表示相关结构或枚举。
- `PlayerActivityInfo_ActivityPetTripData`；含义：玩家 / 活动 / 信息 / 活动 / 宠物 / 旅行 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `PlayerActivityInfo_ActivityPhotoContest`；含义：玩家 / 活动 / 信息 / 活动 / 照片 / 比赛，属于协议消息或数据结构，通常表示相关结构或枚举。
- `PlayerActivityInfo_ActivityPhotoContest_Phase`；含义：玩家 / 活动 / 信息 / 活动 / 照片 / 比赛 / Phase，属于协议消息或数据结构，通常表示相关结构或枚举。
- `PlayerActivityInfo_ActivityPhotoContest_PhotoInfo`；含义：玩家 / 活动 / 信息 / 活动 / 照片 / 比赛 / 照片 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `PlayerActivityInfo_ActivityRecallBPData`；含义：玩家 / 活动 / 信息 / 活动 / 回流 / BP / 数据，属于协议消息或数据结构，通常表示数据结构。
- `PlayerActivityInfo_ActivityRecallData`；含义：玩家 / 活动 / 信息 / 活动 / 回流 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `PlayerActivityInfo_ActivityRecallStarlightData`；含义：玩家 / 活动 / 信息 / 活动 / 回流 / Starlight / 数据，属于协议消息或数据结构，通常表示数据结构。
- `PlayerActivityInfo_ActivitySignRewardData`；含义：玩家 / 活动 / 信息 / 活动 / 签到 / 奖励 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `PlayerActivityInfo_ActivityWeekendChallengeData`；含义：玩家 / 活动 / 信息 / 活动 / 周末 / 挑战 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `PlayerActivityInfo_PreDownloadData`；含义：玩家 / 活动 / 信息 / 预 / 下载 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `RecallBPReward`；含义：回流 / BP / 奖励，属于协议消息或数据结构，通常表示相关结构或枚举。
- `RecallBPTask`；含义：回流 / BP / Task，属于协议消息或数据结构，通常表示相关结构或枚举。

### com_badge_trial.proto
- `BadgeTrialData`；含义：Badge / 试炼 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `GrassTrialChallengeData`；含义：草系 / 试炼 / 挑战 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `GrassTrialData`；含义：草系 / 试炼 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `GrassTrialEventSelected`；含义：草系 / 试炼 / 事件 / Selected，属于协议消息或数据结构，通常表示相关结构或枚举。
- `GrassTrialFusedSkillData`；含义：草系 / 试炼 / Fused / Skill / 数据，属于协议消息或数据结构，通常表示数据结构。
- `GrassTrialHandbookSlotReward`；含义：草系 / 试炼 / 图鉴 / Slot / 奖励，属于协议消息或数据结构，通常表示相关结构或枚举。
- `GrassTrialHandbookSlotState`；含义：草系 / 试炼 / 图鉴 / Slot / 状态，属于协议消息或数据结构，通常表示状态枚举或状态结构。
- `GrassTrialLogSceneRecord`；含义：草系 / 试炼 / Log / 场景 / Record，属于协议消息或数据结构，通常表示相关结构或枚举。
- `GrassTrialNodeEvent`；含义：草系 / 试炼 / 节点 / 事件，属于协议消息或数据结构，通常表示相关结构或枚举。
- `GrassTrialNodeRecord`；含义：草系 / 试炼 / 节点 / Record，属于协议消息或数据结构，通常表示相关结构或枚举。
- `GrassTrialNodeSelection`；含义：草系 / 试炼 / 节点 / Selection，属于协议消息或数据结构，通常表示相关结构或枚举。
- `GrassTrialPeriodData`；含义：草系 / 试炼 / Period / 数据，属于协议消息或数据结构，通常表示数据结构。
- `GrassTrialPeriodReward`；含义：草系 / 试炼 / Period / 奖励，属于协议消息或数据结构，通常表示相关结构或枚举。
- `GrassTrialPet`；含义：草系 / 试炼 / 宠物，属于协议消息或数据结构，通常表示相关结构或枚举。
- `GrassTrialProgressData`；含义：草系 / 试炼 / Progress / 数据，属于协议消息或数据结构，通常表示数据结构。
- `GrassTrialReviewRecord`；含义：草系 / 试炼 / Review / Record，属于协议消息或数据结构，通常表示相关结构或枚举。
- `GrassTrialReviewSkillInfo`；含义：草系 / 试炼 / Review / Skill / 信息，属于协议消息或数据结构，通常表示信息结构。

### com_battle.proto
- `GrassBadgeTrialInfo`；含义：草系 / Badge / 试炼 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `PetRealInfo`；含义：宠物 / Real / 信息，属于协议消息或数据结构，通常表示信息结构。
- `SpecBattleDifficultyItemInfo`；含义：Spec / 战斗 / Difficulty / Item / 信息，属于协议消息或数据结构，通常表示信息结构。

### com_cs_rankboard.proto
- `BaseRankExtData`；含义：基础 / 排行 / Ext / 数据，属于协议消息或数据结构，通常表示数据结构。
- `CSRankUser`；含义：CS / 排行 / User，属于协议消息或数据结构，通常表示相关结构或枚举。
- `PhotoContestRankExtData`；含义：照片 / 比赛 / 排行 / Ext / 数据，属于协议消息或数据结构，通常表示数据结构。
- `PvpRankExtData`；含义：Pvp / 排行 / Ext / 数据，属于协议消息或数据结构，通常表示数据结构。
- `RankEstimatedData`；含义：排行 / Estimated / 数据，属于协议消息或数据结构，通常表示数据结构。
- `RankExtData`；含义：排行 / Ext / 数据，属于协议消息或数据结构，通常表示数据结构。
- `RankUserInfo`；含义：排行 / User / 信息，属于协议消息或数据结构，通常表示信息结构。
- `RankboardKey`；含义：排行榜 / Key，属于协议消息或数据结构，通常表示相关结构或枚举。

### com_debug_draw.proto
- `DebugDrawParams`；含义：Debug / Draw / Params，属于协议消息或数据结构，通常表示相关结构或枚举。

### com_friend_data.proto
- `FriendInteractEvent`；含义：好友 / 互动 / 事件，属于协议消息或数据结构，通常表示相关结构或枚举。
- `FriendInteractRecord`；含义：好友 / 互动 / Record，属于协议消息或数据结构，通常表示相关结构或枚举。
- `FriendInteractRecordList`；含义：好友 / 互动 / Record / 列表，属于协议消息或数据结构，通常表示相关结构或枚举。
- `FriendRecommendInfo`；含义：好友 / 推荐 / 信息，属于协议消息或数据结构，通常表示信息结构。

### com_handbook.proto
- `PetHandbookSeasonInfo`；含义：宠物 / 图鉴 / 赛季 / 信息，属于协议消息或数据结构，通常表示信息结构。

### com_match.proto
- `Pvp_MuteGroups`；含义：Pvp / Mute / Groups，属于协议消息或数据结构，通常表示相关结构或枚举。

### com_misc.proto
- `OfflineOperationConsumeState`；含义：离线 / 操作 / Consume / 状态，属于协议消息或数据结构，通常表示状态枚举或状态结构。

### com_pet.proto
- `PetBackTrackRecordInfo`；含义：宠物 / Back / 追踪 / Record / 信息，属于协议消息或数据结构，通常表示信息结构。
- `PetBacktrackShowInfo`；含义：宠物 / Backtrack / Show / 信息，属于协议消息或数据结构，通常表示信息结构。
- `PetLLMNatureTagInfo`；含义：宠物 / LLM / Nature / 标签 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `PetLLMSingleNatureTagInfo`；含义：宠物 / LLM / Single / Nature / 标签 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `PetLLMTagHistoryInfo`；含义：宠物 / LLM / 标签 / History / 信息，属于协议消息或数据结构，通常表示信息结构。
- `PetReportBriefInfo`；含义：宠物 / Report / Brief / 信息，属于协议消息或数据结构，通常表示信息结构。

### com_player.proto
- `ActivityPetTripLotteryRecord`；含义：活动 / 宠物 / 旅行 / 抽奖 / Record，属于协议消息或数据结构，通常表示相关结构或枚举。
- `BagItemExpireInfo`；含义：Bag / Item / Expire / 信息，属于协议消息或数据结构，通常表示信息结构。
- `BagItemExpireList`；含义：Bag / Item / Expire / 列表，属于协议消息或数据结构，通常表示相关结构或枚举。
- `IdipMailSerialInfo`；含义：Idip / Mail / Serial / 信息，属于协议消息或数据结构，通常表示信息结构。
- `IdipMailSerialList`；含义：Idip / Mail / Serial / 列表，属于协议消息或数据结构，通常表示相关结构或枚举。
- `LotteryRewardRecord`；含义：抽奖 / 奖励 / Record，属于协议消息或数据结构，通常表示相关结构或枚举。
- `OptReWardNumInfo`；含义：Opt / Re / Ward / Num / 信息，属于协议消息或数据结构，通常表示信息结构。
- `OptReWardNumList`；含义：Opt / Re / Ward / Num / 列表，属于协议消息或数据结构，通常表示相关结构或枚举。
- `PlayerNpcLotteryData`；含义：玩家 / NPC / 抽奖 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `SeasonCatchRewardInfo`；含义：赛季 / 捕获 / 奖励 / 信息，属于协议消息或数据结构，通常表示信息结构。

### com_player_data.proto
- `PlayerCardBriefInfo_PetInfo`；含义：玩家 / Card / Brief / 信息 / 宠物 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `PlayerPhotoAlbumInfo`；含义：玩家 / 照片 / Album / 信息，属于协议消息或数据结构，通常表示信息结构。

### com_player_social_info.proto
- `PlayerBattlePassSocialInfo`；含义：玩家 / 战斗 / Pass / Social / 信息，属于协议消息或数据结构，通常表示信息结构。

### com_scene.proto
- `SceneFriendInfoCache`；含义：场景 / 好友 / 信息 / Cache，属于协议消息或数据结构，通常表示相关结构或枚举。

### com_scene_ai.proto
- `AvatarAbnormalStatusInfo`；含义：玩家角色 / 异常 / 状态 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `LLM_PETS_BehaviorReportInfo`；含义：LLM / PETS / Behavior / Report / 信息，属于协议消息或数据结构，通常表示信息结构。
- `LLM_PETS_FollowPetInfo`；含义：LLM / PETS / Follow / 宠物 / 信息，属于协议消息或数据结构，通常表示信息结构。

### com_season.proto
- `BoxMonsterInfo`；含义：盒子 / Monster / 信息，属于协议消息或数据结构，通常表示信息结构。
- `SeasonBattleInfo`；含义：赛季 / 战斗 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `SeasonPetInfo`；含义：赛季 / 宠物 / 信息，属于协议消息或数据结构，通常表示信息结构。

### space_action.proto
- `SpaceAct_AIMutualPerformStateChanged`；含义：Space / Act / AI / Mutual / Perform / 状态 / Changed，属于协议消息或数据结构，通常表示相关结构或枚举。
- `SpaceAct_AbnormalStatusChangeNtf`；含义：Space / Act / 异常 / 状态 / 变化 / Ntf，属于协议消息或数据结构，通常表示相关结构或枚举。
- `SpaceAct_BonusCatchLimitTips`；含义：Space / Act / 奖励 / 捕获 / Limit / Tips，属于协议消息或数据结构，通常表示相关结构或枚举。
- `SpaceAct_CameraSkinChange`；含义：Space / Act / Camera / Skin / 变化，属于协议消息或数据结构，通常表示相关结构或枚举。
- `SpaceAct_LLMDebug`；含义：Space / Act / LLM / Debug，属于协议消息或数据结构，通常表示相关结构或枚举。
- `SpaceAct_LLMDebug.SpaceAct_LLMDebug_InnerData`；含义：Space / Act / LLM / Debug / Space / Act / LLM / Debug / Inner / 数据，属于协议消息或数据结构，通常表示数据结构。
- `SpaceAct_LLM_PETS_BehaviorNotify`；含义：Space / Act / LLM / PETS / Behavior / 通知，属于协议消息或数据结构，通常表示通知消息。
- `SpaceAct_LLM_PETS_BehaviorNotify.BehaviorInfo`；含义：Space / Act / LLM / PETS / Behavior / 通知 / Behavior / 信息，属于协议消息或数据结构，通常表示信息结构。
- `SpaceAct_LLM_PETS_QueryPets`；含义：Space / Act / LLM / PETS / Query / Pets，属于协议消息或数据结构，通常表示相关结构或枚举。
- `SpaceAct_NpcMutationInfoChange`；含义：Space / Act / NPC / 变异 / 信息 / 变化，属于协议消息或数据结构，通常表示相关结构或枚举。
- `SpaceAct_NpcSizeScaleChange`；含义：Space / Act / NPC / Size / Scale / 变化，属于协议消息或数据结构，通常表示相关结构或枚举。
- `SpaceAct_OptionBlackOrWhiteListUinsChgNtf`；含义：Space / Act / 选项 / 黑 / Or / 白 / 列表 / Uins / Chg / Ntf，属于协议消息或数据结构，通常表示相关结构或枚举。
- `SpaceAct_PlayChatBubble`；含义：Space / Act / Play / Chat / Bubble，属于协议消息或数据结构，通常表示相关结构或枚举。
- `SpaceAct_PlayerTagsChange`；含义：Space / Act / 玩家 / Tags / 变化，属于协议消息或数据结构，通常表示相关结构或枚举。
- `SpaceAct_RoleplayHoldInfoChgNtf`；含义：Space / Act / 角色扮演 / 持有 / 信息 / Chg / Ntf，属于协议消息或数据结构，通常表示相关结构或枚举。

### space_data.proto
- `AIMutualPerformStateInfo`；含义：AI / Mutual / Perform / 状态 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ActorCompData_AbnormalStatus`；含义：场景对象 / 组件 / 数据 / 异常 / 状态，属于协议消息或数据结构，通常表示状态枚举或状态结构。
- `ActorCompData_CatchBonusCtrl`；含义：场景对象 / 组件 / 数据 / 捕获 / 奖励 / Ctrl，属于协议消息或数据结构，通常表示相关结构或枚举。
- `ActorCompData_LlmAgent`；含义：场景对象 / 组件 / 数据 / Llm / Agent，属于协议消息或数据结构，通常表示相关结构或枚举。
- `ActorCompData_NpcInfoChange`；含义：场景对象 / 组件 / 数据 / NPC / 信息 / 变化，属于协议消息或数据结构，通常表示相关结构或枚举。
- `ActorCompData_NpcProp`；含义：场景对象 / 组件 / 数据 / NPC / Prop，属于协议消息或数据结构，通常表示相关结构或枚举。
- `ActorCompData_RoleplayProp`；含义：场景对象 / 组件 / 数据 / 角色扮演 / Prop，属于协议消息或数据结构，通常表示相关结构或枚举。
- `ActorInfo_AvatarAI`；含义：场景对象 / 信息 / 玩家角色 / AI，属于协议消息或数据结构，通常表示相关结构或枚举。
- `ActorInfo_AvatarCamera`；含义：场景对象 / 信息 / 玩家角色 / Camera，属于协议消息或数据结构，通常表示相关结构或枚举。
- `ActorInfo_NpcProp`；含义：场景对象 / 信息 / NPC / Prop，属于协议消息或数据结构，通常表示相关结构或枚举。
- `ActorInfo_RoleplayPropInfo`；含义：场景对象 / 信息 / 角色扮演 / Prop / 信息，属于协议消息或数据结构，通常表示信息结构。
- `AvatarEnterdPropInfo`；含义：玩家角色 / Enterd / Prop / 信息，属于协议消息或数据结构，通常表示信息结构。
- `AvatarFriendRecommendInfo`；含义：玩家角色 / 好友 / 推荐 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `BonusContainerCfgRecord`；含义：奖励 / Container / Cfg / Record，属于协议消息或数据结构，通常表示相关结构或枚举。
- `BonusGiftConditionTypeData`；含义：奖励 / 礼物 / 条件 / 类型 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `BoxData`；含义：盒子 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `C1PersistData`；含义：C / 1 / Persist / 数据，属于协议消息或数据结构，通常表示数据结构。
- `C2GiftCondData`；含义：C / 2 / 礼物 / 条件 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `C2PersistData`；含义：C / 2 / Persist / 数据，属于协议消息或数据结构，通常表示数据结构。
- `CellCompData_AreaDetector`；含义：格子 / 组件 / 数据 / Area / Detector，属于协议消息或数据结构，通常表示相关结构或枚举。
- `CircusPetParams`；含义：Circus / 宠物 / Params，属于协议消息或数据结构，通常表示相关结构或枚举。
- `CompExtendData`；含义：组件 / Extend / 数据，属于协议消息或数据结构，通常表示数据结构。
- `CompExtendDatas`；含义：组件 / Extend / Datas，属于协议消息或数据结构，通常表示相关结构或枚举。
- `LLMPetBehaviorGroupInfo`；含义：LLM / 宠物 / Behavior / Group / 信息，属于协议消息或数据结构，通常表示信息结构。
- `LlmAgent_AvatarInfo`；含义：Llm / Agent / 玩家角色 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `LlmAgent_PetInfo`；含义：Llm / Agent / 宠物 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `NpcGuardLimitData`；含义：NPC / Guard / Limit / 数据，属于协议消息或数据结构，通常表示数据结构。
- `NpcInfoChangeData`；含义：NPC / 信息 / 变化 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `NpcInfoChangeRetryData`；含义：NPC / 信息 / 变化 / Retry / 数据，属于协议消息或数据结构，通常表示数据结构。
- `NpcOptionData_CooldownInfo`；含义：NPC / 选项 / 数据 / Cooldown / 信息，属于协议消息或数据结构，通常表示信息结构。
- `NpcOptionStashExtraData`；含义：NPC / 选项 / Stash / Extra / 数据，属于协议消息或数据结构，通常表示数据结构。
- `NpcPropSlotData`；含义：NPC / Prop / Slot / 数据，属于协议消息或数据结构，通常表示数据结构。
- `NpcPropSlotInfo`；含义：NPC / Prop / Slot / 信息，属于协议消息或数据结构，通常表示信息结构。
- `OldFlavorSceneRequiredPlayerInfo`；含义：Old / Flavor / 场景 / 所需 / 玩家 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ResonanceInfo`；含义：Resonance / 信息，属于协议消息或数据结构，通常表示信息结构。
- `SceneCorrectedPlayerInfo`；含义：场景 / Corrected / 玩家 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `SceneDungeonCorrectedPlayerInfo`；含义：场景 / Dungeon / Corrected / 玩家 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `TakePhotoEmojiPoseSyncInfo`；含义：Take / 照片 / Emoji / Pose / 同步 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ThrowCatchResultData`；含义：Throw / 捕获 / 结果 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `TransformStoryFlagData`；含义：Transform / Story / Flag / 数据，属于协议消息或数据结构，通常表示数据结构。

### zone_gm.proto
- `ZoneGMTestSuggestionPlayerOne`；含义：Zone 服务 / GM / Test / Suggestion / 玩家 / One，属于协议消息或数据结构，通常表示相关结构或枚举。
- `ZoneGmAddTestSuggestionPlayersReq`；含义：Zone 服务 / Gm / 添加 / Test / Suggestion / Players / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGmAddTestSuggestionPlayersRsp`；含义：Zone 服务 / Gm / 添加 / Test / Suggestion / Players / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGmClientNotify`；含义：Zone 服务 / Gm / Client / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneGmClientResponseReq`；含义：Zone 服务 / Gm / Client / Response / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGmClientResponseRsp`；含义：Zone 服务 / Gm / Client / Response / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGmDistrGoodsReq`；含义：Zone 服务 / Gm / Distr / Goods / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGmDistrGoodsRsp`；含义：Zone 服务 / Gm / Distr / Goods / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGmExecClientGmReq`；含义：Zone 服务 / Gm / Exec / Client / Gm / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGmExecClientGmRsp`；含义：Zone 服务 / Gm / Exec / Client / Gm / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGmLlmPetsBehaviorEvalReq`；含义：Zone 服务 / Gm / Llm / Pets / Behavior / Eval / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGmLlmPetsBehaviorEvalRsp`；含义：Zone 服务 / Gm / Llm / Pets / Behavior / Eval / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGmSetGlobalChallengeProgressReq`；含义：Zone 服务 / Gm / 设置 / 全局 / 挑战 / Progress / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGmSetGlobalChallengeProgressRsp`；含义：Zone 服务 / Gm / 设置 / 全局 / 挑战 / Progress / 响应，属于协议消息或数据结构，通常表示响应消息。

### zonesvr.proto
- `SelectBattlePassThemeFriendsInfo`；含义：选择 / 战斗 / Pass / Theme / Friends / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ZoneActivityPetTripAddPetReq`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 添加 / 宠物 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPetTripAddPetRsp`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 添加 / 宠物 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPetTripAutoTripReq`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 自动 / 旅行 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPetTripAutoTripRsp`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 自动 / 旅行 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPetTripGetLotteryResultReq`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 获取 / 抽奖 / 结果 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPetTripGetLotteryResultRsp`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 获取 / 抽奖 / 结果 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPetTripGetWishChoiceCountReq`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 获取 / 心愿 / 选择 / 数量 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPetTripGetWishChoiceCountRsp`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 获取 / 心愿 / 选择 / 数量 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPetTripGetWishChoiceCountRsp.WishChoiceCountInfo`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 获取 / 心愿 / 选择 / 数量 / 响应 / 心愿 / 选择 / 数量 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ZoneActivityPetTripReceiveLotteryRewardReq`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 领取 / 抽奖 / 奖励 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPetTripReceiveLotteryRewardRsp`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 领取 / 抽奖 / 奖励 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPetTripSetWishChoiceReq`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 设置 / 心愿 / 选择 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPetTripSetWishChoiceRsp`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 设置 / 心愿 / 选择 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPhotoContestEvaluationNotify`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 评审 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneActivityPhotoContestEvaluationNotify.PhotoInfo`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 评审 / 通知 / 照片 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ZoneActivityPhotoContestEvaluationReq`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 评审 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPhotoContestEvaluationRsp`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 评审 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPhotoContestHotReq`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 热门 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPhotoContestHotRsp`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 热门 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPhotoContestLikeNotify`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 点赞 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneActivityPhotoContestLikeNotify.PhotoLikeInfo`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 点赞 / 通知 / 照片 / 点赞 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ZoneActivityPhotoContestLikeReq`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 点赞 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPhotoContestLikeRsp`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 点赞 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPhotoContestSubmitReq`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 提交 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPhotoContestSubmitRewardNotify`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 提交 / 奖励 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneActivityPhotoContestSubmitRsp`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 提交 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPopupPlayedReq`；含义：Zone 服务 / 活动 / Popup / Played / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPopupPlayedRsp`；含义：Zone 服务 / 活动 / Popup / Played / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPredownloadReadyReq`；含义：Zone 服务 / 活动 / Predownload / Ready / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPredownloadReadyRsp`；含义：Zone 服务 / 活动 / Predownload / Ready / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityRecallTagSwitchReq`；含义：Zone 服务 / 活动 / 回流 / 标签 / 开关 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityRecallTagSwitchRsp`；含义：Zone 服务 / 活动 / 回流 / 标签 / 开关 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivitySaveRecommendPetTeamReq`；含义：Zone 服务 / 活动 / Save / 推荐 / 宠物 / Team / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivitySaveRecommendPetTeamRsp`；含义：Zone 服务 / 活动 / Save / 推荐 / 宠物 / Team / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneAiAttackAbnormalStatusReq`；含义：Zone 服务 / AI / Attack / 异常 / 状态 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneAiAttackAbnormalStatusRsp`；含义：Zone 服务 / AI / Attack / 异常 / 状态 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneAiCoachRecommendLineupNotify`；含义：Zone 服务 / AI / 教练 / 推荐 / 阵容 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneAiCoachRecommendLineupReq`；含义：Zone 服务 / AI / 教练 / 推荐 / 阵容 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneAiCoachRecommendLineupRsp`；含义：Zone 服务 / AI / 教练 / 推荐 / 阵容 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneAiCoachRequestCancelReq`；含义：Zone 服务 / AI / 教练 / Request / 取消 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneAiCoachRequestCancelRsp`；含义：Zone 服务 / AI / 教练 / Request / 取消 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneAiCoachSetStatusReq`；含义：Zone 服务 / AI / 教练 / 设置 / 状态 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneAiCoachSetStatusRsp`；含义：Zone 服务 / AI / 教练 / 设置 / 状态 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneAiCoachWhiteListReq`；含义：Zone 服务 / AI / 教练 / 白 / 列表 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneAiCoachWhiteListRsp`；含义：Zone 服务 / AI / 教练 / 白 / 列表 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneBacktrackPetReq`；含义：Zone 服务 / Backtrack / 宠物 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneBacktrackPetRsp`；含义：Zone 服务 / Backtrack / 宠物 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneBacktrackPetRsp.RewardItem`；含义：Zone 服务 / Backtrack / 宠物 / 响应 / 奖励 / Item，属于协议消息或数据结构，通常表示相关结构或枚举。
- `ZoneBagItemExpireCheckReq`；含义：Zone 服务 / Bag / Item / Expire / Check / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneBagItemExpireCheckRsp`；含义：Zone 服务 / Bag / Item / Expire / Check / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneBagItemExpireConvertReq`；含义：Zone 服务 / Bag / Item / Expire / Convert / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneBagItemExpireConvertRsp`；含义：Zone 服务 / Bag / Item / Expire / Convert / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneDistributeBillNotify`；含义：Zone 服务 / Distribute / Bill / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneGetActivityOptionalPetsReq`；含义：Zone 服务 / 获取 / 活动 / Optional / Pets / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetActivityOptionalPetsRsp`；含义：Zone 服务 / 获取 / 活动 / Optional / Pets / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetAreaIdReq`；含义：Zone 服务 / 获取 / Area / Id / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetAreaIdRsp`；含义：Zone 服务 / 获取 / Area / Id / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetDistributeBillReq`；含义：Zone 服务 / 获取 / Distribute / Bill / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetDistributeBillRsp`；含义：Zone 服务 / 获取 / Distribute / Bill / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetHandbookSeasonAwardReq`；含义：Zone 服务 / 获取 / 图鉴 / 赛季 / Award / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetHandbookSeasonAwardRsp`；含义：Zone 服务 / 获取 / 图鉴 / 赛季 / Award / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetPetInfoByGidReq`；含义：Zone 服务 / 获取 / 宠物 / 信息 / By / Gid / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetPetInfoByGidRsp`；含义：Zone 服务 / 获取 / 宠物 / 信息 / By / Gid / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetRankUserListReq`；含义：Zone 服务 / 获取 / 排行 / User / 列表 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetRankUserListRsp`；含义：Zone 服务 / 获取 / 排行 / User / 列表 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetRankUserReq`；含义：Zone 服务 / 获取 / 排行 / User / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetRankUserRsp`；含义：Zone 服务 / 获取 / 排行 / User / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetSelectAnotherBattlePassThemeFriendsReq`；含义：Zone 服务 / 获取 / 选择 / Another / 战斗 / Pass / Theme / Friends / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetSelectAnotherBattlePassThemeFriendsRsp`；含义：Zone 服务 / 获取 / 选择 / Another / 战斗 / Pass / Theme / Friends / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGmClearDungeonReq`；含义：Zone 服务 / Gm / Clear / Dungeon / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGmClearDungeonRsp`；含义：Zone 服务 / Gm / Clear / Dungeon / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialAbandonChallengeReq`；含义：Zone 服务 / 草系 / 试炼 / Abandon / 挑战 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialAbandonChallengeRsp`；含义：Zone 服务 / 草系 / 试炼 / Abandon / 挑战 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialChallengeDataSyncNotify`；含义：Zone 服务 / 草系 / 试炼 / 挑战 / 数据 / 同步 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneGrassTrialChallengeSettleNotify`；含义：Zone 服务 / 草系 / 试炼 / 挑战 / Settle / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneGrassTrialEnterSceneReq`；含义：Zone 服务 / 草系 / 试炼 / Enter / 场景 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialEnterSceneRsp`；含义：Zone 服务 / 草系 / 试炼 / Enter / 场景 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialGetInfoReq`；含义：Zone 服务 / 草系 / 试炼 / 获取 / 信息 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialGetInfoRsp`；含义：Zone 服务 / 草系 / 试炼 / 获取 / 信息 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialHandleRewardNotify`；含义：Zone 服务 / 草系 / 试炼 / Handle / 奖励 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneGrassTrialHandleRewardReq`；含义：Zone 服务 / 草系 / 试炼 / Handle / 奖励 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialHandleRewardRsp`；含义：Zone 服务 / 草系 / 试炼 / Handle / 奖励 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialNextNodeReq`；含义：Zone 服务 / 草系 / 试炼 / Next / 节点 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialNextNodeRsp`；含义：Zone 服务 / 草系 / 试炼 / Next / 节点 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialNodeRefreshReq`；含义：Zone 服务 / 草系 / 试炼 / 节点 / 刷新 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialNodeRefreshRsp`；含义：Zone 服务 / 草系 / 试炼 / 节点 / 刷新 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialPauseChallengeReq`；含义：Zone 服务 / 草系 / 试炼 / Pause / 挑战 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialPauseChallengeRsp`；含义：Zone 服务 / 草系 / 试炼 / Pause / 挑战 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialResumeChallengeReq`；含义：Zone 服务 / 草系 / 试炼 / Resume / 挑战 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialResumeChallengeRsp`；含义：Zone 服务 / 草系 / 试炼 / Resume / 挑战 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialSelectEventReq`；含义：Zone 服务 / 草系 / 试炼 / 选择 / 事件 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialSelectEventRsp`；含义：Zone 服务 / 草系 / 试炼 / 选择 / 事件 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialStartChallengeReq`；含义：Zone 服务 / 草系 / 试炼 / Start / 挑战 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialStartChallengeRsp`；含义：Zone 服务 / 草系 / 试炼 / Start / 挑战 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneLlmPetsAvailablePetsReq`；含义：Zone 服务 / Llm / Pets / Available / Pets / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneLlmPetsAvailablePetsRsp`；含义：Zone 服务 / Llm / Pets / Available / Pets / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneLlmPetsBehaviorReportReq`；含义：Zone 服务 / Llm / Pets / Behavior / Report / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneLlmPetsBehaviorReportRsp`；含义：Zone 服务 / Llm / Pets / Behavior / Report / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZonePlayerActivityDropAreaNotify`；含义：Zone 服务 / 玩家 / 活动 / Drop / Area / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZonePlayerBattlePassExpNotify`；含义：Zone 服务 / 玩家 / 战斗 / Pass / 经验 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneQueryBacktrackPetRewardReq`；含义：Zone 服务 / Query / Backtrack / 宠物 / 奖励 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneQueryBacktrackPetRewardRsp`；含义：Zone 服务 / Query / Backtrack / 宠物 / 奖励 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneQueryBacktrackPetRewardRsp.RewardItem`；含义：Zone 服务 / Query / Backtrack / 宠物 / 奖励 / 响应 / 奖励 / Item，属于协议消息或数据结构，通常表示相关结构或枚举。
- `ZoneReceiveActivityRecallBpExpReq`；含义：Zone 服务 / 领取 / 活动 / 回流 / Bp / 经验 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneReceiveActivityRecallBpExpRsp`；含义：Zone 服务 / 领取 / 活动 / 回流 / Bp / 经验 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneReceiveActivityRecallBpLevelRewardReq`；含义：Zone 服务 / 领取 / 活动 / 回流 / Bp / 等级 / 奖励 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneReceiveActivityRecallBpLevelRewardRsp`；含义：Zone 服务 / 领取 / 活动 / 回流 / Bp / 等级 / 奖励 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneReportDistributeReq`；含义：Zone 服务 / Report / Distribute / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneReportDistributeRsp`；含义：Zone 服务 / Report / Distribute / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneRptMonthCardTipsShowReq`；含义：Zone 服务 / Rpt / Month / Card / Tips / Show / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneRptMonthCardTipsShowRsp`；含义：Zone 服务 / Rpt / Month / Card / Tips / Show / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneChangeNpcSizeScaleReq`；含义：Zone 服务 / 场景 / 变化 / NPC / Size / Scale / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneChangeNpcSizeScaleRsp`；含义：Zone 服务 / 场景 / 变化 / NPC / Size / Scale / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneCreateRoleplayPropReq`；含义：Zone 服务 / 场景 / 创建 / 角色扮演 / Prop / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneCreateRoleplayPropRsp`；含义：Zone 服务 / 场景 / 创建 / 角色扮演 / Prop / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneRecycleRoleplayPropReq`；含义：Zone 服务 / 场景 / Recycle / 角色扮演 / Prop / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneRecycleRoleplayPropRsp`；含义：Zone 服务 / 场景 / Recycle / 角色扮演 / Prop / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneThrowCatchFinishReq`；含义：Zone 服务 / 场景 / Throw / 捕获 / Finish / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneThrowCatchFinishRsp`；含义：Zone 服务 / 场景 / Throw / 捕获 / Finish / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneUnlockActivityRecallPaidRewardReq`；含义：Zone 服务 / 解锁 / 活动 / 回流 / 付费 / 奖励 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneUnlockActivityRecallPaidRewardRsp`；含义：Zone 服务 / 解锁 / 活动 / 回流 / 付费 / 奖励 / 响应，属于协议消息或数据结构，通常表示响应消息。

### zonesvr_notify.proto
- `ZonePlayerNpcLotteryGoodsRewardNotify`；含义：Zone 服务 / 玩家 / NPC / 抽奖 / Goods / 奖励 / 通知，属于协议消息或数据结构，通常表示通知消息。

## 按文件统计的删除 message

### space_data.proto
- `CellCompData_EffectDetector`；含义：场景格子的效果检测器组件数据。

### world_map.proto
- `ZoneSceneBeginSyncWorldMapInfoReq`；含义：开始同步世界地图信息请求。
- `ZoneSceneBeginSyncWorldMapInfoRsp`；含义：开始同步世界地图信息响应。
- `ZoneSceneEndSyncWorldMapInfoReq`；含义：结束同步世界地图信息请求。
- `ZoneSceneEndSyncWorldMapInfoRsp`；含义：结束同步世界地图信息响应。
- `ZoneSceneTickWorldMapInfoSyncReq`；含义：周期性同步世界地图信息请求。
- `ZoneSceneTickWorldMapInfoSyncRsp`；含义：周期性同步世界地图信息响应。

### zonesvr.proto
- `ZoneBadgeChallengeEnterReq`；含义：Zone 服务 / Badge / 挑战 / Enter / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneBadgeChallengeEnterRsp`；含义：Zone 服务 / Badge / 挑战 / Enter / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneBadgeChallengeSelectUpgradeReq`；含义：Zone 服务 / Badge / 挑战 / 选择 / Upgrade / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneBadgeChallengeSelectUpgradeRsp`；含义：Zone 服务 / Badge / 挑战 / 选择 / Upgrade / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneCancelTaskRedPointReq`；含义：Zone 服务 / 取消 / Task / Red / Point / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneCancelTaskRedPointRsp`；含义：Zone 服务 / 取消 / Task / Red / Point / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneChangeTaskSwitchDataReq`；含义：Zone 服务 / 变化 / Task / 开关 / 数据 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneChangeTaskSwitchDataRsp`；含义：Zone 服务 / 变化 / Task / 开关 / 数据 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneCheckColorSuitStateReq`；含义：Zone 服务 / Check / Color / Suit / 状态 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneCheckColorSuitStateRsp`；含义：Zone 服务 / Check / Color / Suit / 状态 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneClearDungeonReq`；含义：Zone 服务 / Clear / Dungeon / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneClearDungeonRsp`；含义：Zone 服务 / Clear / Dungeon / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneFeedVideoDelUploadFileReq`；含义：Zone 服务 / Feed / Video / Del / Upload / File / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneFeedVideoDelUploadFileRsp`；含义：Zone 服务 / Feed / Video / Del / Upload / File / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneFeedVideoFeedbackReq`；含义：Zone 服务 / Feed / Video / Feedback / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneFeedVideoFeedbackRsp`；含义：Zone 服务 / Feed / Video / Feedback / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetAppearanceInfoReq`；含义：Zone 服务 / 获取 / Appearance / 信息 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetAppearanceInfoRsp`；含义：Zone 服务 / 获取 / Appearance / 信息 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetCampFruitNpcInfosReq`；含义：Zone 服务 / 获取 / Camp / Fruit / NPC / Infos / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetCampFruitNpcInfosRsp`；含义：Zone 服务 / 获取 / Camp / Fruit / NPC / Infos / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetClaimableGlassTintReq`；含义：Zone 服务 / 获取 / Claimable / Glass / Tint / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetClaimableGlassTintRsp`；含义：Zone 服务 / 获取 / Claimable / Glass / Tint / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetHandbookStatReq`；含义：Zone 服务 / 获取 / 图鉴 / Stat / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetHandbookStatRsp`；含义：Zone 服务 / 获取 / 图鉴 / Stat / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetSubTaskTokenTriggeredTaskInfoReq`；含义：Zone 服务 / 获取 / Sub / Task / Token / Triggered / Task / 信息 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetSubTaskTokenTriggeredTaskInfoRsp`；含义：Zone 服务 / 获取 / Sub / Task / Token / Triggered / Task / 信息 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetTaskSwitchDataReq`；含义：Zone 服务 / 获取 / Task / 开关 / 数据 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetTaskSwitchDataRsp`；含义：Zone 服务 / 获取 / Task / 开关 / 数据 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneHeartbeatReq`；含义：Zone 服务 / Heartbeat / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneHeartbeatRsp`；含义：Zone 服务 / Heartbeat / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneHomePetFoodCompoundReq`；含义：Zone 服务 / Home / 宠物 / Food / Compound / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneHomePetFoodCompoundRsp`；含义：Zone 服务 / Home / 宠物 / Food / Compound / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneJudgePayReq`；含义：Zone 服务 / Judge / Pay / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneJudgePayRsp`；含义：Zone 服务 / Judge / Pay / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneLogoutReq`；含义：Zone 服务 / Logout / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneLogoutRsp`；含义：Zone 服务 / Logout / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneModifyBagListSortReq`；含义：Zone 服务 / Modify / Bag / 列表 / Sort / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneModifyBagListSortRsp`；含义：Zone 服务 / Modify / Bag / 列表 / Sort / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZonePetBasePointAssignReq`；含义：Zone 服务 / 宠物 / 基础 / Point / Assign / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZonePetBasePointAssignReq.BasePointInfo`；含义：Zone 服务 / 宠物 / 基础 / Point / Assign / 请求 / 基础 / Point / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ZonePetBasePointAssignRsp`；含义：Zone 服务 / 宠物 / 基础 / Point / Assign / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZonePetDeleteReq`；含义：Zone 服务 / 宠物 / Delete / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZonePetDeleteRsp`；含义：Zone 服务 / 宠物 / Delete / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZonePetSetFollowReq`；含义：Zone 服务 / 宠物 / 设置 / Follow / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZonePetSetFollowRsp`；含义：Zone 服务 / 宠物 / 设置 / Follow / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZonePetUseBagItemReq`；含义：Zone 服务 / 宠物 / Use / Bag / Item / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZonePetUseBagItemReq.BagItemInfo`；含义：Zone 服务 / 宠物 / Use / Bag / Item / 请求 / Bag / Item / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ZonePetUseBagItemRsp`；含义：Zone 服务 / 宠物 / Use / Bag / Item / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZonePublishVideoToWechatReq`；含义：Zone 服务 / Publish / Video / To / Wechat / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZonePublishVideoToWechatRsp`；含义：Zone 服务 / Publish / Video / To / Wechat / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneQueryAdventureChapterReq`；含义：Zone 服务 / Query / Adventure / Chapter / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneQueryAdventureChapterRsp`；含义：Zone 服务 / Query / Adventure / Chapter / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneQuerySceneTaskStatReq`；含义：Zone 服务 / Query / 场景 / Task / Stat / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneQuerySceneTaskStatRsp`；含义：Zone 服务 / Query / 场景 / Task / Stat / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneRefreshBadgeChallengeCardReq`；含义：Zone 服务 / 刷新 / Badge / 挑战 / Card / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneRefreshBadgeChallengeCardRsp`；含义：Zone 服务 / 刷新 / Badge / 挑战 / Card / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneApplyVisitConfirmReq`；含义：Zone 服务 / 场景 / Apply / Visit / Confirm / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneApplyVisitConfirmRsp`；含义：Zone 服务 / 场景 / Apply / Visit / Confirm / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneApplyVisitListQueryReq`；含义：Zone 服务 / 场景 / Apply / Visit / 列表 / Query / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneApplyVisitListQueryRsp`；含义：Zone 服务 / 场景 / Apply / Visit / 列表 / Query / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneApplyVisitListQueryRsp.ApplyInfo`；含义：Zone 服务 / 场景 / Apply / Visit / 列表 / Query / 响应 / Apply / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ZoneSceneApplyVisitReq`；含义：Zone 服务 / 场景 / Apply / Visit / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneApplyVisitRsp`；含义：Zone 服务 / 场景 / Apply / Visit / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneCastSceneSkillReq`；含义：Zone 服务 / 场景 / Cast / 场景 / Skill / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneCastSceneSkillRsp`；含义：Zone 服务 / 场景 / Cast / 场景 / Skill / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneChangeMoveModeReq`；含义：Zone 服务 / 场景 / 变化 / Move / Mode / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneChangeMoveModeRsp`；含义：Zone 服务 / 场景 / 变化 / Move / Mode / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneGeneralOpReq`；含义：Zone 服务 / 场景 / General / Op / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneGeneralOpRsp`；含义：Zone 服务 / 场景 / General / Op / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneNpcBattleSeriesReq`；含义：Zone 服务 / 场景 / NPC / 战斗 / Series / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneNpcBattleSeriesRsp`；含义：Zone 服务 / 场景 / NPC / 战斗 / Series / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneSetAvatarPosReq`；含义：Zone 服务 / 场景 / 设置 / 玩家角色 / Pos / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneSetAvatarPosRsp`；含义：Zone 服务 / 场景 / 设置 / 玩家角色 / Pos / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneStrongStormNty`；含义：Zone 服务 / 场景 / Strong / Storm / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneSceneThrowCollisionReq`；含义：Zone 服务 / 场景 / Throw / Collision / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneThrowCollisionRsp`；含义：Zone 服务 / 场景 / Throw / Collision / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatHitReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Hit / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatHitRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Hit / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillBuffReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Buff / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillBuffRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Buff / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillCastReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Cast / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillCastRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Cast / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillEndReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / 结束 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillEndRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / 结束 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillFireBulletReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Fire / Bullet / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillFireBulletRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Fire / Bullet / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillJumpEndReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Jump / 结束 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillJumpEndRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Jump / 结束 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillJumpReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Jump / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillJumpRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Jump / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillPetCollisionReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / 宠物 / Collision / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillPetCollisionRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / 宠物 / Collision / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillRcdReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Rcd / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillRcdRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Rcd / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillSpawnBulletReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Spawn / Bullet / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillSpawnBulletRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Spawn / Bullet / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillSpawnNpcReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Spawn / NPC / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillSpawnNpcRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Spawn / NPC / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSecondaryPasswordActionCheckReq`；含义：Zone 服务 / Secondary / Password / 动作 / Check / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSecondaryPasswordActionCheckRsp`；含义：Zone 服务 / Secondary / Password / 动作 / Check / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSecondaryPasswordCancelFreeReq`；含义：Zone 服务 / Secondary / Password / 取消 / Free / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSecondaryPasswordCancelFreeRsp`；含义：Zone 服务 / Secondary / Password / 取消 / Free / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSyncTempReq`；含义：Zone 服务 / 同步 / Temp / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSyncTempRsp`；含义：Zone 服务 / 同步 / Temp / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneTaskTraceReq`；含义：Zone 服务 / Task / Trace / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneTaskTraceRsp`；含义：Zone 服务 / Task / Trace / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneTlogReportReq`；含义：Zone 服务 / Tlog / Report / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneTlogReportRsp`；含义：Zone 服务 / Tlog / Report / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneTssMessageCheckReq`；含义：Zone 服务 / Tss / 消息 / Check / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneTssMessageCheckRsp`；含义：Zone 服务 / Tss / 消息 / Check / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneVodVideoSignatureReq`；含义：Zone 服务 / Vod / Video / Signature / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneVodVideoSignatureRsp`；含义：Zone 服务 / Vod / Video / Signature / 响应，属于协议消息或数据结构，通常表示响应消息。

## 按文件统计的新增 enum

### com_action.proto
- `RoleplayHoldInfoChangeReason`；含义：角色扮演持有物信息变化原因。

### com_badge_trial.proto
- `NodeRefreshType`；含义：节点刷新类型。
- `RewardAction`；含义：奖励处理动作。

### com_battle_enum.proto
- `BoxType`；含义：盒子类型。
- `PetAttrType`；含义：宠物属性类型。
- `PetMutationType`；含义：宠物变异类型。
- `PetRarityType`；含义：宠物稀有度类型。

### com_cs_rankboard.proto
- `RankboardConst`；含义：排行榜常量。

### com_friend_data.proto
- `FriendInteractEventType`；含义：好友互动事件类型。

### com_handbook.proto
- `PetHandbookSeasonPetType`；含义：宠物图鉴赛季宠物类型。

### com_misc.proto
- `MarqueeSource`；含义：跑马灯来源。

### com_player_data.proto
- `AiCoachStatus`；含义：AI 教练状态。
- `PlayerTag`；含义：玩家标签。

### errorcode.proto
- `MOBA_RET.ActivitySvrErr`；含义：活动服务器错误码。
- `MOBA_RET.LLMSvrErr`；含义：LLM 服务器错误码。
- `MOBA_RET.OfflineOperationErr`；含义：离线操作错误码。
- `MOBA_RET.RankboardErr`；含义：排行榜错误码。

### space_data.proto
- `DungeonStageState`；含义：Dungeon / Stage / 状态，属于枚举定义，通常表示状态枚举或状态结构。

### xls_enum.proto
- `AIcoachSceneType`；含义：AI 教练场景类型。
- `AbnormalStatusType`；含义：异常状态类型。
- `ActivityContentRefresh`；含义：活动内容刷新类型或刷新规则。
- `BonusBoxIconType`；含义：奖励宝箱图标类型。
- `BonusGiftConditionType`；含义：奖励礼物条件类型。
- `BonusPoolType`；含义：奖励池类型。
- `BonusRefreshType`；含义：奖励刷新类型。
- `ChildMessageMagic`；含义：子消息魔法类型。
- `DefaultTrackType`；含义：默认追踪类型。
- `DlgSelectDisableCond`；含义：对话选项禁用条件。
- `EnumHeadWearType`；含义：头饰类型。
- `EventType`；含义：事件类型。
- `FashionBottomsTag`；含义：时装下装标签。
- `FashionShoesTag`；含义：时装鞋子标签。
- `FashionSocksTag`；含义：时装袜子标签。
- `FashionWandSource`；含义：时装魔杖来源。
- `FilterSeasonPet`；含义：赛季宠物筛选类型。
- `FriendRecommendSource`；含义：好友推荐来源。
- `GameplayAiState`；含义：玩法 AI 状态。
- `GlobalCountType`；含义：全局计数类型。
- `GrassTrialEffect`；含义：草系试炼效果。
- `GrassTrialEffectType`；含义：草系试炼效果类型。
- `GrassTrialFusionType`；含义：草系试炼融合类型。
- `GrassTrialState`；含义：草系试炼状态。
- `GuideActionBanType`；含义：引导动作禁用类型。
- `LotteryMoniterEvent`；含义：抽奖 / Moniter / 事件，属于枚举定义，通常表示相关结构或枚举。
- `LotteryPoolType`；含义：抽奖 / 池 / 类型，属于枚举定义，通常表示类型枚举。
- `LotteryPoolValidationCheck`；含义：抽奖 / 池 / Validation / Check，属于枚举定义，通常表示相关结构或枚举。
- `MailSubType`；含义：Mail / Sub / 类型，属于枚举定义，通常表示类型枚举。
- `NpcInfoChangeFixNpcType`；含义：NPC / 信息 / 变化 / Fix / NPC / 类型，属于枚举定义，通常表示类型枚举。
- `NpcInfoChangeFixType`；含义：NPC / 信息 / 变化 / Fix / 类型，属于枚举定义，通常表示类型枚举。
- `NpcInfoChangeSuccessCostType`；含义：NPC / 信息 / 变化 / Success / Cost / 类型，属于枚举定义，通常表示类型枚举。
- `NpcOptionCooldownType`；含义：NPC / 选项 / Cooldown / 类型，属于枚举定义，通常表示类型枚举。
- `NpcSizeChangeType`；含义：NPC / Size / 变化 / 类型，属于枚举定义，通常表示类型枚举。
- `PETStoryPageType`；含义：PET / Story / Page / 类型，属于枚举定义，通常表示类型枚举。
- `PetBoxTidyRuleType`；含义：宠物 / 盒子 / Tidy / Rule / 类型，属于枚举定义，通常表示类型枚举。
- `PetSotryDecorationImage`；含义：宠物 / Sotry / Decoration / Image，属于枚举定义，通常表示相关结构或枚举。
- `PetSotryDecorationImageTxt`；含义：宠物 / Sotry / Decoration / Image / Txt，属于枚举定义，通常表示相关结构或枚举。
- `PlayerTransformType`；含义：玩家 / Transform / 类型，属于枚举定义，通常表示类型枚举。
- `PutPropType`；含义：Put / Prop / 类型，属于枚举定义，通常表示类型枚举。
- `RarityLevelEnumeration`；含义：稀有度 / 等级 / Enumeration，属于枚举定义，通常表示相关结构或枚举。
- `RecallPetEggType`；含义：回流 / 宠物 / Egg / 类型，属于枚举定义，通常表示类型枚举。
- `RollBack`；含义：Roll / Back，属于枚举定义，通常表示相关结构或枚举。
- `SceneSitBlurType`；含义：场景 / Sit / Blur / 类型，属于枚举定义，通常表示类型枚举。
- `SpecialGoodsType`；含义：Special / Goods / 类型，属于枚举定义，通常表示类型枚举。
- `TaskGoRetentionType`；含义：Task / Go / Retention / 类型，属于枚举定义，通常表示类型枚举。
- `VictoryCondition`；含义：Victory / 条件，属于枚举定义，通常表示相关结构或枚举。
- `WeightFixType`；含义：Weight / Fix / 类型，属于枚举定义，通常表示类型枚举。

## 按文件统计的删除 enum

### xls_enum.proto
- `GmBitFlag`；含义：Gm / Bit / Flag，属于枚举定义，通常表示相关结构或枚举。

## ZoneSvrCmd 命令枚举变化

新增命令号：114
- 653: `ZONE_GET_HANDBOOK_SEASON_AWARD_REQ`；含义：获取 / 图鉴 / SEASON / AWARD / 请求，属于 Zone 服务命令号，请求命令。
- 654: `ZONE_GET_HANDBOOK_SEASON_AWARD_RSP`；含义：获取 / 图鉴 / SEASON / AWARD / 响应，属于 Zone 服务命令号，响应命令。
- 790: `ZONE_GET_SELECT_ANOTHER_BATTLE_PASS_THEME_FRIENDS_REQ`；含义：获取 / 选择 / ANOTHER / 战斗 / PASS / THEME / FRIENDS / 请求，属于 Zone 服务命令号，请求命令。
- 791: `ZONE_GET_SELECT_ANOTHER_BATTLE_PASS_THEME_FRIENDS_RSP`；含义：获取 / 选择 / ANOTHER / 战斗 / PASS / THEME / FRIENDS / 响应，属于 Zone 服务命令号，响应命令。
- 1167: `ZONE_GET_RANK_USER_REQ`；含义：获取 / 排行榜 / 用户 / 请求，属于 Zone 服务命令号，请求命令。
- 1168: `ZONE_GET_RANK_USER_RSP`；含义：获取 / 排行榜 / 用户 / 响应，属于 Zone 服务命令号，响应命令。
- 1169: `ZONE_GET_RANK_USER_LIST_REQ`；含义：获取 / 排行榜 / 用户 / 列表 / 请求，属于 Zone 服务命令号，请求命令。
- 1170: `ZONE_GET_RANK_USER_LIST_RSP`；含义：获取 / 排行榜 / 用户 / 列表 / 响应，属于 Zone 服务命令号，响应命令。
- 1223: `ZONE_PLAYER_NPC_LOTTERY_GOODS_REWARD_NOTIFY`；含义：玩家 / NPC / 抽奖 / GOODS / 奖励 / 通知，属于 Zone 服务命令号，通知命令。
- 1224: `ZONE_PLAYER_ACTIVITY_DROP_AREA_NOTIFY`；含义：玩家 / 活动 / DROP / 区域 / 通知，属于 Zone 服务命令号，通知命令。
- 4935: `ZONE_GET_PET_INFO_BY_GID_REQ`；含义：获取 / 宠物 / 信息 / BY / GID / 请求，属于 Zone 服务命令号，请求命令。
- 4936: `ZONE_GET_PET_INFO_BY_GID_RSP`；含义：获取 / 宠物 / 信息 / BY / GID / 响应，属于 Zone 服务命令号，响应命令。
- 6376: `ZONE_ACTIVITY_PHOTO_CONTEST_SUBMIT_REQ`；含义：活动 / 照片 / 比赛 / SUBMIT / 请求，属于 Zone 服务命令号，请求命令。
- 6377: `ZONE_ACTIVITY_PHOTO_CONTEST_SUBMIT_RSP`；含义：活动 / 照片 / 比赛 / SUBMIT / 响应，属于 Zone 服务命令号，响应命令。
- 6378: `ZONE_ACTIVITY_PHOTO_CONTEST_EVALUATION_REQ`；含义：活动 / 照片 / 比赛 / 评审 / 请求，属于 Zone 服务命令号，请求命令。
- 6379: `ZONE_ACTIVITY_PHOTO_CONTEST_EVALUATION_RSP`；含义：活动 / 照片 / 比赛 / 评审 / 响应，属于 Zone 服务命令号，响应命令。
- 6380: `ZONE_ACTIVITY_PHOTO_CONTEST_LIKE_REQ`；含义：活动 / 照片 / 比赛 / 点赞 / 请求，属于 Zone 服务命令号，请求命令。
- 6381: `ZONE_ACTIVITY_PHOTO_CONTEST_LIKE_RSP`；含义：活动 / 照片 / 比赛 / 点赞 / 响应，属于 Zone 服务命令号，响应命令。
- 6390: `ZONE_ACTIVITY_SELECT_TRACK_CONTENTS_REQ`；含义：活动 / 选择 / 跟踪 / 内容 / 请求，属于 Zone 服务命令号，请求命令。
- 6391: `ZONE_ACTIVITY_SELECT_TRACK_CONTENTS_RSP`；含义：活动 / 选择 / 跟踪 / 内容 / 响应，属于 Zone 服务命令号，响应命令。
- 6392: `ZONE_ACTIVITY_POPUP_PLAYED_REQ`；含义：活动 / 弹窗 / PLAYED / 请求，属于 Zone 服务命令号，请求命令。
- 6393: `ZONE_ACTIVITY_POPUP_PLAYED_RSP`；含义：活动 / 弹窗 / PLAYED / 响应，属于 Zone 服务命令号，响应命令。
- 6394: `ZONE_BACKTRACK_PET_REQ`；含义：BACKTRACK / 宠物 / 请求，属于 Zone 服务命令号，请求命令。
- 6395: `ZONE_BACKTRACK_PET_RSP`；含义：BACKTRACK / 宠物 / 响应，属于 Zone 服务命令号，响应命令。
- 6396: `ZONE_QUERY_BACKTRACK_PET_REWARD_REQ`；含义：查询 / BACKTRACK / 宠物 / 奖励 / 请求，属于 Zone 服务命令号，请求命令。
- 6397: `ZONE_QUERY_BACKTRACK_PET_REWARD_RSP`；含义：查询 / BACKTRACK / 宠物 / 奖励 / 响应，属于 Zone 服务命令号，响应命令。
- 6400: `ZONE_LLM_PETS_AVAILABLE_PETS_REQ`；含义：LLM / PETS / AVAILABLE / PETS / 请求，属于 Zone 服务命令号，请求命令。
- 6401: `ZONE_LLM_PETS_AVAILABLE_PETS_RSP`；含义：LLM / PETS / AVAILABLE / PETS / 响应，属于 Zone 服务命令号，响应命令。
- 6402: `ZONE_LLM_PETS_BEHAVIOR_REPORT_REQ`；含义：LLM / PETS / BEHAVIOR / 上报 / 请求，属于 Zone 服务命令号，请求命令。
- 6403: `ZONE_LLM_PETS_BEHAVIOR_REPORT_RSP`；含义：LLM / PETS / BEHAVIOR / 上报 / 响应，属于 Zone 服务命令号，响应命令。
- 6405: `ZONE_ACTIVITY_SAVE_RECOMMEND_PET_TEAM_REQ`；含义：活动 / 保存 / 推荐 / 宠物 / 队伍 / 请求，属于 Zone 服务命令号，请求命令。
- 6406: `ZONE_ACTIVITY_SAVE_RECOMMEND_PET_TEAM_RSP`；含义：活动 / 保存 / 推荐 / 宠物 / 队伍 / 响应，属于 Zone 服务命令号，响应命令。
- 6407: `ZONE_AI_COACH_SET_STATUS_REQ`；含义：AI / 教练 / 设置 / 状态 / 请求，属于 Zone 服务命令号，请求命令。
- 6408: `ZONE_AI_COACH_SET_STATUS_RSP`；含义：AI / 教练 / 设置 / 状态 / 响应，属于 Zone 服务命令号，响应命令。
- 6409: `ZONE_AI_COACH_WHITE_LIST_REQ`；含义：AI / 教练 / WHITE / 列表 / 请求，属于 Zone 服务命令号，请求命令。
- 6410: `ZONE_AI_COACH_WHITE_LIST_RSP`；含义：AI / 教练 / WHITE / 列表 / 响应，属于 Zone 服务命令号，响应命令。
- 6411: `ZONE_AI_COACH_RECOMMEND_LINEUP_REQ`；含义：AI / 教练 / 推荐 / LINEUP / 请求，属于 Zone 服务命令号，请求命令。
- 6412: `ZONE_AI_COACH_RECOMMEND_LINEUP_RSP`；含义：AI / 教练 / 推荐 / LINEUP / 响应，属于 Zone 服务命令号，响应命令。
- 6413: `ZONE_AI_COACH_RECOMMEND_LINEUP_NOTIFY`；含义：AI / 教练 / 推荐 / LINEUP / 通知，属于 Zone 服务命令号，通知命令。
- 6414: `ZONE_ACTIVITY_PHOTO_CONTEST_HOT_REQ`；含义：活动 / 照片 / 比赛 / 热门 / 请求，属于 Zone 服务命令号，请求命令。
- 6415: `ZONE_ACTIVITY_PHOTO_CONTEST_HOT_RSP`；含义：活动 / 照片 / 比赛 / 热门 / 响应，属于 Zone 服务命令号，响应命令。
- 6416: `ZONE_AI_COACH_REQUEST_CANCEL_REQ`；含义：AI / 教练 / REQUEST / 取消 / 请求，属于 Zone 服务命令号，请求命令。
- 6417: `ZONE_AI_COACH_REQUEST_CANCEL_RSP`；含义：AI / 教练 / REQUEST / 取消 / 响应，属于 Zone 服务命令号，响应命令。
- 6431: `ZONE_ACTIVITY_PHOTO_CONTEST_SUBMIT_REWARD_NOTIFY`；含义：活动 / 照片 / 比赛 / SUBMIT / 奖励 / 通知，属于 Zone 服务命令号，通知命令。
- 6432: `ZONE_ACTIVITY_PET_TRIP_ADD_PET_REQ`；含义：活动 / 宠物 / 旅行 / 添加 / 宠物 / 请求，属于 Zone 服务命令号，请求命令。
- 6433: `ZONE_ACTIVITY_PET_TRIP_ADD_PET_RSP`；含义：活动 / 宠物 / 旅行 / 添加 / 宠物 / 响应，属于 Zone 服务命令号，响应命令。
- 6434: `ZONE_ACTIVITY_PET_TRIP_AUTO_TRIP_REQ`；含义：活动 / 宠物 / 旅行 / 自动 / 旅行 / 请求，属于 Zone 服务命令号，请求命令。
- 6435: `ZONE_ACTIVITY_PET_TRIP_AUTO_TRIP_RSP`；含义：活动 / 宠物 / 旅行 / 自动 / 旅行 / 响应，属于 Zone 服务命令号，响应命令。
- 6436: `ZONE_ACTIVITY_PET_TRIP_SET_WISH_CHOICE_REQ`；含义：活动 / 宠物 / 旅行 / 设置 / 心愿 / 选择 / 请求，属于 Zone 服务命令号，请求命令。
- 6437: `ZONE_ACTIVITY_PET_TRIP_SET_WISH_CHOICE_RSP`；含义：活动 / 宠物 / 旅行 / 设置 / 心愿 / 选择 / 响应，属于 Zone 服务命令号，响应命令。
- 6438: `ZONE_ACTIVITY_PET_TRIP_RECEIVE_LOTTERY_REWARD_REQ`；含义：活动 / 宠物 / 旅行 / 领取 / 抽奖 / 奖励 / 请求，属于 Zone 服务命令号，请求命令。
- 6439: `ZONE_ACTIVITY_PET_TRIP_RECEIVE_LOTTERY_REWARD_RSP`；含义：活动 / 宠物 / 旅行 / 领取 / 抽奖 / 奖励 / 响应，属于 Zone 服务命令号，响应命令。
- 6440: `ZONE_ACTIVITY_PET_TRIP_GET_WISH_CHOICE_COUNT_REQ`；含义：活动 / 宠物 / 旅行 / 获取 / 心愿 / 选择 / 数量 / 请求，属于 Zone 服务命令号，请求命令。
- 6441: `ZONE_ACTIVITY_PET_TRIP_GET_WISH_CHOICE_COUNT_RSP`；含义：活动 / 宠物 / 旅行 / 获取 / 心愿 / 选择 / 数量 / 响应，属于 Zone 服务命令号，响应命令。
- 6442: `ZONE_RECEIVE_ACTIVITY_RECALL_BP_EXP_REQ`；含义：领取 / 活动 / 回流 / BP / EXP / 请求，属于 Zone 服务命令号，请求命令。
- 6443: `ZONE_RECEIVE_ACTIVITY_RECALL_BP_EXP_RSP`；含义：领取 / 活动 / 回流 / BP / EXP / 响应，属于 Zone 服务命令号，响应命令。
- 6444: `ZONE_RECEIVE_ACTIVITY_RECALL_BP_LEVEL_REWARD_REQ`；含义：领取 / 活动 / 回流 / BP / 等级 / 奖励 / 请求，属于 Zone 服务命令号，请求命令。
- 6445: `ZONE_RECEIVE_ACTIVITY_RECALL_BP_LEVEL_REWARD_RSP`；含义：领取 / 活动 / 回流 / BP / 等级 / 奖励 / 响应，属于 Zone 服务命令号，响应命令。
- 6446: `ZONE_UNLOCK_ACTIVITY_RECALL_PAID_REWARD_REQ`；含义：解锁 / 活动 / 回流 / 付费 / 奖励 / 请求，属于 Zone 服务命令号，请求命令。
- 6447: `ZONE_UNLOCK_ACTIVITY_RECALL_PAID_REWARD_RSP`；含义：解锁 / 活动 / 回流 / 付费 / 奖励 / 响应，属于 Zone 服务命令号，响应命令。
- 6448: `ZONE_GET_ACTIVITY_OPTIONAL_PETS_REQ`；含义：获取 / 活动 / 可选 / PETS / 请求，属于 Zone 服务命令号，请求命令。
- 6449: `ZONE_GET_ACTIVITY_OPTIONAL_PETS_RSP`；含义：获取 / 活动 / 可选 / PETS / 响应，属于 Zone 服务命令号，响应命令。
- 6450: `ZONE_ACTIVITY_RECALL_TAG_SWITCH_REQ`；含义：活动 / 回流 / 标签 / 开关 / 请求，属于 Zone 服务命令号，请求命令。
- 6451: `ZONE_ACTIVITY_RECALL_TAG_SWITCH_RSP`；含义：活动 / 回流 / 标签 / 开关 / 响应，属于 Zone 服务命令号，响应命令。
- 6464: `ZONE_ACTIVITY_PET_TRIP_GET_LOTTERY_RESULT_REQ`；含义：活动 / 宠物 / 旅行 / 获取 / 抽奖 / RESULT / 请求，属于 Zone 服务命令号，请求命令。
- 6465: `ZONE_ACTIVITY_PET_TRIP_GET_LOTTERY_RESULT_RSP`；含义：活动 / 宠物 / 旅行 / 获取 / 抽奖 / RESULT / 响应，属于 Zone 服务命令号，响应命令。
- 6466: `ZONE_PLAYER_BATTLE_PASS_EXP_NOTIFY`；含义：玩家 / 战斗 / PASS / EXP / 通知，属于 Zone 服务命令号，通知命令。
- 6467: `ZONE_GET_AREA_ID_REQ`；含义：获取 / 区域 / ID / 请求，属于 Zone 服务命令号，请求命令。
- 6468: `ZONE_GET_AREA_ID_RSP`；含义：获取 / 区域 / ID / 响应，属于 Zone 服务命令号，响应命令。
- 6469: `ZONE_ACTIVITY_PREDOWNLOAD_READY_REQ`；含义：活动 / PREDOWNLOAD / 准备完成 / 请求，属于 Zone 服务命令号，请求命令。
- 6470: `ZONE_ACTIVITY_PREDOWNLOAD_READY_RSP`；含义：活动 / PREDOWNLOAD / 准备完成 / 响应，属于 Zone 服务命令号，响应命令。
- 6480: `ZONE_GRASS_TRIAL_START_CHALLENGE_REQ`；含义：草系 / 试炼 / 开始 / 挑战 / 请求，属于 Zone 服务命令号，请求命令。
- 6481: `ZONE_GRASS_TRIAL_START_CHALLENGE_RSP`；含义：草系 / 试炼 / 开始 / 挑战 / 响应，属于 Zone 服务命令号，响应命令。
- 6482: `ZONE_GRASS_TRIAL_ENTER_SCENE_REQ`；含义：草系 / 试炼 / 进入 / 场景 / 请求，属于 Zone 服务命令号，请求命令。
- 6483: `ZONE_GRASS_TRIAL_ENTER_SCENE_RSP`；含义：草系 / 试炼 / 进入 / 场景 / 响应，属于 Zone 服务命令号，响应命令。
- 6484: `ZONE_SCENE_CREATE_ROLEPLAY_PROP_REQ`；含义：场景 / CREATE / ROLEPLAY / PROP / 请求，属于 Zone 服务命令号，请求命令。
- 6485: `ZONE_SCENE_CREATE_ROLEPLAY_PROP_RSP`；含义：场景 / CREATE / ROLEPLAY / PROP / 响应，属于 Zone 服务命令号，响应命令。
- 6486: `ZONE_SCENE_RECYCLE_ROLEPLAY_PROP_REQ`；含义：场景 / RECYCLE / ROLEPLAY / PROP / 请求，属于 Zone 服务命令号，请求命令。
- 6487: `ZONE_SCENE_RECYCLE_ROLEPLAY_PROP_RSP`；含义：场景 / RECYCLE / ROLEPLAY / PROP / 响应，属于 Zone 服务命令号，响应命令。
- 6488: `ZONE_GRASS_TRIAL_GET_INFO_REQ`；含义：草系 / 试炼 / 获取 / 信息 / 请求，属于 Zone 服务命令号，请求命令。
- 6489: `ZONE_GRASS_TRIAL_GET_INFO_RSP`；含义：草系 / 试炼 / 获取 / 信息 / 响应，属于 Zone 服务命令号，响应命令。
- 6490: `ZONE_GRASS_TRIAL_ABANDON_CHALLENGE_REQ`；含义：草系 / 试炼 / ABANDON / 挑战 / 请求，属于 Zone 服务命令号，请求命令。
- 6491: `ZONE_GRASS_TRIAL_ABANDON_CHALLENGE_RSP`；含义：草系 / 试炼 / ABANDON / 挑战 / 响应，属于 Zone 服务命令号，响应命令。
- 6492: `ZONE_GRASS_TRIAL_CHALLENGE_DATA_SYNC_NOTIFY`；含义：草系 / 试炼 / 挑战 / 数据 / 同步 / 通知，属于 Zone 服务命令号，通知命令。
- 6493: `ZONE_GRASS_TRIAL_PAUSE_CHALLENGE_REQ`；含义：草系 / 试炼 / PAUSE / 挑战 / 请求，属于 Zone 服务命令号，请求命令。
- 6494: `ZONE_GRASS_TRIAL_PAUSE_CHALLENGE_RSP`；含义：草系 / 试炼 / PAUSE / 挑战 / 响应，属于 Zone 服务命令号，响应命令。
- 6495: `ZONE_GRASS_TRIAL_RESUME_CHALLENGE_REQ`；含义：草系 / 试炼 / RESUME / 挑战 / 请求，属于 Zone 服务命令号，请求命令。
- 6496: `ZONE_GRASS_TRIAL_RESUME_CHALLENGE_RSP`；含义：草系 / 试炼 / RESUME / 挑战 / 响应，属于 Zone 服务命令号，响应命令。
- 6497: `ZONE_GRASS_TRIAL_NEXT_NODE_REQ`；含义：草系 / 试炼 / NEXT / 节点 / 请求，属于 Zone 服务命令号，请求命令。
- 6498: `ZONE_GRASS_TRIAL_NEXT_NODE_RSP`；含义：草系 / 试炼 / NEXT / 节点 / 响应，属于 Zone 服务命令号，响应命令。
- 6499: `ZONE_GRASS_TRIAL_SELECT_EVENT_REQ`；含义：草系 / 试炼 / 选择 / EVENT / 请求，属于 Zone 服务命令号，请求命令。
- 6500: `ZONE_GRASS_TRIAL_SELECT_EVENT_RSP`；含义：草系 / 试炼 / 选择 / EVENT / 响应，属于 Zone 服务命令号，响应命令。
- 6501: `ZONE_GRASS_TRIAL_NODE_REFRESH_REQ`；含义：草系 / 试炼 / 节点 / 刷新 / 请求，属于 Zone 服务命令号，请求命令。
- 6502: `ZONE_GRASS_TRIAL_NODE_REFRESH_RSP`；含义：草系 / 试炼 / 节点 / 刷新 / 响应，属于 Zone 服务命令号，响应命令。
- 6503: `ZONE_GRASS_TRIAL_HANDLE_REWARD_NOTIFY`；含义：草系 / 试炼 / HANDLE / 奖励 / 通知，属于 Zone 服务命令号，通知命令。
- 6504: `ZONE_GRASS_TRIAL_HANDLE_REWARD_REQ`；含义：草系 / 试炼 / HANDLE / 奖励 / 请求，属于 Zone 服务命令号，请求命令。
- 6505: `ZONE_GRASS_TRIAL_HANDLE_REWARD_RSP`；含义：草系 / 试炼 / HANDLE / 奖励 / 响应，属于 Zone 服务命令号，响应命令。
- 6528: `ZONE_SCENE_CHANGE_NPC_SIZE_SCALE_REQ`；含义：场景 / 改变 / NPC / SIZE / SCALE / 请求，属于 Zone 服务命令号，请求命令。
- 6529: `ZONE_SCENE_CHANGE_NPC_SIZE_SCALE_RSP`；含义：场景 / 改变 / NPC / SIZE / SCALE / 响应，属于 Zone 服务命令号，响应命令。
- 6530: `ZONE_SCENE_THROW_CATCH_FINISH_REQ`；含义：场景 / 投掷 / CATCH / 完成 / 请求，属于 Zone 服务命令号，请求命令。
- 6531: `ZONE_SCENE_THROW_CATCH_FINISH_RSP`；含义：场景 / 投掷 / CATCH / 完成 / 响应，属于 Zone 服务命令号，响应命令。
- 6532: `ZONE_AI_ATTACK_ABNORMAL_STATUS_REQ`；含义：AI / ATTACK / ABNORMAL / 状态 / 请求，属于 Zone 服务命令号，请求命令。
- 6533: `ZONE_AI_ATTACK_ABNORMAL_STATUS_RSP`；含义：AI / ATTACK / ABNORMAL / 状态 / 响应，属于 Zone 服务命令号，响应命令。
- 6534: `ZONE_BAG_ITEM_EXPIRE_CONVERT_REQ`；含义：背包 / 道具 / 过期 / 转换 / 请求，属于 Zone 服务命令号，请求命令。
- 6535: `ZONE_BAG_ITEM_EXPIRE_CONVERT_RSP`；含义：背包 / 道具 / 过期 / 转换 / 响应，属于 Zone 服务命令号，响应命令。
- 6536: `ZONE_BAG_ITEM_EXPIRE_CHECK_REQ`；含义：背包 / 道具 / 过期 / 检查 / 请求，属于 Zone 服务命令号，请求命令。
- 6537: `ZONE_BAG_ITEM_EXPIRE_CHECK_RSP`；含义：背包 / 道具 / 过期 / 检查 / 响应，属于 Zone 服务命令号，响应命令。
- 6570: `ZONE_GET_DISTRIBUTE_BILL_REQ`；含义：获取 / 分发 / 账单 / 请求，属于 Zone 服务命令号，请求命令。
- 6571: `ZONE_GET_DISTRIBUTE_BILL_RSP`；含义：获取 / 分发 / 账单 / 响应，属于 Zone 服务命令号，响应命令。
- 6572: `ZONE_DISTRIBUTE_BILL_NOTIFY`；含义：分发 / 账单 / 通知，属于 Zone 服务命令号，通知命令。
- 6573: `ZONE_REPORT_DISTRIBUTE_REQ`；含义：上报 / 分发 / 请求，属于 Zone 服务命令号，请求命令。
- 6574: `ZONE_REPORT_DISTRIBUTE_RSP`；含义：上报 / 分发 / 响应，属于 Zone 服务命令号，响应命令。
- 6575: `ZONE_RPT_MONTH_CARD_TIPS_SHOW_REQ`；含义：RPT / 月 / 卡牌 / 提示 / 展示 / 请求，属于 Zone 服务命令号，请求命令。
- 6576: `ZONE_RPT_MONTH_CARD_TIPS_SHOW_RSP`；含义：RPT / 月 / 卡牌 / 提示 / 展示 / 响应，属于 Zone 服务命令号，响应命令。

删除命令号：148
- 261: `ZONE_LOGOUT_REQ`；含义：登出 / 请求，属于 Zone 服务命令号，请求命令。
- 262: `ZONE_LOGOUT_RSP`；含义：登出 / 响应，属于 Zone 服务命令号，响应命令。
- 289: `ZONE_HEARTBEAT_REQ`；含义：心跳 / 请求，属于 Zone 服务命令号，请求命令。
- 290: `ZONE_HEARTBEAT_RSP`；含义：心跳 / 响应，属于 Zone 服务命令号，响应命令。
- 341: `ZONE_SCENE_CAST_SCENE_SKILL_REQ`；含义：场景 / 施放 / 场景 / 技能 / 请求，属于 Zone 服务命令号，请求命令。
- 342: `ZONE_SCENE_CAST_SCENE_SKILL_RSP`；含义：场景 / 施放 / 场景 / 技能 / 响应，属于 Zone 服务命令号，响应命令。
- 361: `ZONE_MODIFY_BAG_LIST_SORT_REQ`；含义：MODIFY / 背包 / 列表 / 排序 / 请求，属于 Zone 服务命令号，请求命令。
- 362: `ZONE_MODIFY_BAG_LIST_SORT_RSP`；含义：MODIFY / 背包 / 列表 / 排序 / 响应，属于 Zone 服务命令号，响应命令。
- 387: `ZONE_PET_USE_BAG_ITEM_REQ`；含义：宠物 / 使用 / 背包 / 道具 / 请求，属于 Zone 服务命令号，请求命令。
- 388: `ZONE_PET_USE_BAG_ITEM_RSP`；含义：宠物 / 使用 / 背包 / 道具 / 响应，属于 Zone 服务命令号，响应命令。
- 389: `ZONE_PET_BASE_POINT_ASSIGN_REQ`；含义：宠物 / 基础 / 点数 / 分配 / 请求，属于 Zone 服务命令号，请求命令。
- 390: `ZONE_PET_BASE_POINT_ASSIGN_RSP`；含义：宠物 / 基础 / 点数 / 分配 / 响应，属于 Zone 服务命令号，响应命令。
- 393: `ZONE_PET_SET_FOLLOW_REQ`；含义：宠物 / 设置 / 跟随 / 请求，属于 Zone 服务命令号，请求命令。
- 394: `ZONE_PET_SET_FOLLOW_RSP`；含义：宠物 / 设置 / 跟随 / 响应，属于 Zone 服务命令号，响应命令。
- 397: `ZONE_PET_DELETE_REQ`；含义：宠物 / 删除 / 请求，属于 Zone 服务命令号，请求命令。
- 398: `ZONE_PET_DELETE_RSP`；含义：宠物 / 删除 / 响应，属于 Zone 服务命令号，响应命令。
- 414: `ZONE_TASK_TRACE_REQ`；含义：任务 / 追踪 / 请求，属于 Zone 服务命令号，请求命令。
- 415: `ZONE_TASK_TRACE_RSP`；含义：任务 / 追踪 / 响应，属于 Zone 服务命令号，响应命令。
- 416: `ZONE_SCENE_GENERAL_OP_REQ`；含义：场景 / 通用 / 操作 / 请求，属于 Zone 服务命令号，请求命令。
- 417: `ZONE_SCENE_GENERAL_OP_RSP`；含义：场景 / 通用 / 操作 / 响应，属于 Zone 服务命令号，响应命令。
- 420: `ZONE_SCENE_NPC_BATTLE_SERIES_REQ`；含义：场景 / NPC / 战斗 / 连续 / 请求，属于 Zone 服务命令号，请求命令。
- 421: `ZONE_SCENE_NPC_BATTLE_SERIES_RSP`；含义：场景 / NPC / 战斗 / 连续 / 响应，属于 Zone 服务命令号，响应命令。
- 427: `ZONE_SCENE_SET_BROADCAST_LIMIT_REQ`；含义：场景 / 设置 / BROADCAST / LIMIT / 请求，属于 Zone 服务命令号，请求命令。
- 428: `ZONE_SCENE_SET_BROADCAST_LIMIT_RSP`；含义：场景 / 设置 / BROADCAST / LIMIT / 响应，属于 Zone 服务命令号，响应命令。
- 454: `ZONE_TRACK_TASK_NPC_REQ`；含义：跟踪 / 任务 / NPC / 请求，属于 Zone 服务命令号，请求命令。
- 455: `ZONE_TRACK_TASK_NPC_RSP`；含义：跟踪 / 任务 / NPC / 响应，属于 Zone 服务命令号，响应命令。
- 464: `ZONE_SCENE_BEGIN_SYNC_WORLD_MAP_INFO_REQ`；含义：场景 / 开始 / 同步 / 大世界 / MAP / 信息 / 请求，属于 Zone 服务命令号，请求命令。
- 465: `ZONE_SCENE_BEGIN_SYNC_WORLD_MAP_INFO_RSP`；含义：场景 / 开始 / 同步 / 大世界 / MAP / 信息 / 响应，属于 Zone 服务命令号，响应命令。
- 466: `ZONE_SCENE_END_SYNC_WORLD_MAP_INFO_REQ`；含义：场景 / 结束 / 同步 / 大世界 / MAP / 信息 / 请求，属于 Zone 服务命令号，请求命令。
- 467: `ZONE_SCENE_END_SYNC_WORLD_MAP_INFO_RSP`；含义：场景 / 结束 / 同步 / 大世界 / MAP / 信息 / 响应，属于 Zone 服务命令号，响应命令。
- 468: `ZONE_SCENE_TICK_WORLD_MAP_INFO_SYNC_REQ`；含义：场景 / 周期 / 大世界 / MAP / 信息 / 同步 / 请求，属于 Zone 服务命令号，请求命令。
- 469: `ZONE_SCENE_TICK_WORLD_MAP_INFO_SYNC_RSP`；含义：场景 / 周期 / 大世界 / MAP / 信息 / 同步 / 响应，属于 Zone 服务命令号，响应命令。
- 536: `ZONE_SYNC_TEMP_REQ`；含义：同步 / 临时 / 请求，属于 Zone 服务命令号，请求命令。
- 537: `ZONE_SYNC_TEMP_RSP`；含义：同步 / 临时 / 响应，属于 Zone 服务命令号，响应命令。
- 557: `ZONE_SCENE_THROW_COLLISION_REQ`；含义：场景 / 投掷 / 碰撞 / 请求，属于 Zone 服务命令号，请求命令。
- 558: `ZONE_SCENE_THROW_COLLISION_RSP`；含义：场景 / 投掷 / 碰撞 / 响应，属于 Zone 服务命令号，响应命令。
- 584: `ZONE_BACKPACK_TEAM_UPDATE_REQ`；含义：BACKPACK / 队伍 / 更新 / 请求，属于 Zone 服务命令号，请求命令。
- 585: `ZONE_BACKPACK_TEAM_UPDATE_RSP`；含义：BACKPACK / 队伍 / 更新 / 响应，属于 Zone 服务命令号，响应命令。
- 617: `ZONE_SCENE_CLIENT_VISUALIZATION_REQ`；含义：场景 / 客户端 / VISUALIZATION / 请求，属于 Zone 服务命令号，请求命令。
- 618: `ZONE_SCENE_CLIENT_VISUALIZATION_RSP`；含义：场景 / 客户端 / VISUALIZATION / 响应，属于 Zone 服务命令号，响应命令。
- 623: `ZONE_SCENE_CLIENT_VISUALIZATION_NTY`；含义：场景 / 客户端 / VISUALIZATION / 通知，属于 Zone 服务命令号，通知命令。
- 660: `ZONE_SCENE_STRONG_STORM_NTY`；含义：场景 / 强 / 风暴 / 通知，属于 Zone 服务命令号，通知命令。
- 663: `ZONE_TLOG_REPORT_REQ`；含义：TLog 日志 / 上报 / 请求，属于 Zone 服务命令号，请求命令。
- 664: `ZONE_TLOG_REPORT_RSP`；含义：TLog 日志 / 上报 / 响应，属于 Zone 服务命令号，响应命令。
- 712: `ZONE_JUDGE_PAY_REQ`；含义：判定 / 支付 / 请求，属于 Zone 服务命令号，请求命令。
- 713: `ZONE_JUDGE_PAY_RSP`；含义：判定 / 支付 / 响应，属于 Zone 服务命令号，响应命令。
- 714: `ZONE_SCENE_APPLY_VISIT_REQ`；含义：场景 / 申请 / 访问 / 请求，属于 Zone 服务命令号，请求命令。
- 715: `ZONE_SCENE_APPLY_VISIT_RSP`；含义：场景 / 申请 / 访问 / 响应，属于 Zone 服务命令号，响应命令。
- 727: `ZONE_SCENE_APPLY_VISIT_CONFIRM_REQ`；含义：场景 / 申请 / 访问 / 确认 / 请求，属于 Zone 服务命令号，请求命令。
- 728: `ZONE_SCENE_APPLY_VISIT_CONFIRM_RSP`；含义：场景 / 申请 / 访问 / 确认 / 响应，属于 Zone 服务命令号，响应命令。
- 730: `ZONE_SCENE_APPLY_VISIT_LIST_QUERY_REQ`；含义：场景 / 申请 / 访问 / 列表 / 查询 / 请求，属于 Zone 服务命令号，请求命令。
- 731: `ZONE_SCENE_APPLY_VISIT_LIST_QUERY_RSP`；含义：场景 / 申请 / 访问 / 列表 / 查询 / 响应，属于 Zone 服务命令号，响应命令。
- 783: `ZONE_DOTS_COMPONENT_SYNC_REQ`；含义：DOTS / COMPONENT / 同步 / 请求，属于 Zone 服务命令号，请求命令。
- 784: `ZONE_DOTS_COMPONENT_SYNC_RSP`；含义：DOTS / COMPONENT / 同步 / 响应，属于 Zone 服务命令号，响应命令。
- 787: `ZONE_CLEAR_DUNGEON_REQ`；含义：清理 / 副本 / 请求，属于 Zone 服务命令号，请求命令。
- 788: `ZONE_CLEAR_DUNGEON_RSP`；含义：清理 / 副本 / 响应，属于 Zone 服务命令号，响应命令。
- 813: `ZONE_QUERY_ADVENTURE_CHAPTER_REQ`；含义：查询 / 冒险 / 章节 / 请求，属于 Zone 服务命令号，请求命令。
- 814: `ZONE_QUERY_ADVENTURE_CHAPTER_RSP`；含义：查询 / 冒险 / 章节 / 响应，属于 Zone 服务命令号，响应命令。
- 844: `ZONE_SCENE_TEAM_BATTLE_SELECT_FLOWER_BOSS_REQ`；含义：场景 / 队伍 / 战斗 / 选择 / FLOWER / BOSS / 请求，属于 Zone 服务命令号，请求命令。
- 845: `ZONE_SCENE_TEAM_BATTLE_SELECT_FLOWER_BOSS_RSP`；含义：场景 / 队伍 / 战斗 / 选择 / FLOWER / BOSS / 响应，属于 Zone 服务命令号，响应命令。
- 864: `ZONE_SCENE_CHANGE_MOVE_MODE_REQ`；含义：场景 / 改变 / 移动 / 模式 / 请求，属于 Zone 服务命令号，请求命令。
- 865: `ZONE_SCENE_CHANGE_MOVE_MODE_RSP`；含义：场景 / 改变 / 移动 / 模式 / 响应，属于 Zone 服务命令号，响应命令。
- 868: `ZONE_GET_SUB_TASK_TOKEN_TRIGGERED_TASK_INFO_REQ`；含义：获取 / 子 / 任务 / token / 触发 / 任务 / 信息 / 请求，属于 Zone 服务命令号，请求命令。
- 869: `ZONE_GET_SUB_TASK_TOKEN_TRIGGERED_TASK_INFO_RSP`；含义：获取 / 子 / 任务 / token / 触发 / 任务 / 信息 / 响应，属于 Zone 服务命令号，响应命令。
- 900: `ZONE_SCENE_WORLD_COMBAT_SKILL_CAST_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 施放 / 请求，属于 Zone 服务命令号，请求命令。
- 901: `ZONE_SCENE_WORLD_COMBAT_SKILL_CAST_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 施放 / 响应，属于 Zone 服务命令号，响应命令。
- 902: `ZONE_SCENE_WORLD_COMBAT_SKILL_SPAWN_NPC_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 生成 / NPC / 请求，属于 Zone 服务命令号，请求命令。
- 903: `ZONE_SCENE_WORLD_COMBAT_SKILL_SPAWN_NPC_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 生成 / NPC / 响应，属于 Zone 服务命令号，响应命令。
- 904: `ZONE_SCENE_WORLD_COMBAT_SKILL_SPAWN_BULLET_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 生成 / 子弹 / 请求，属于 Zone 服务命令号，请求命令。
- 905: `ZONE_SCENE_WORLD_COMBAT_SKILL_SPAWN_BULLET_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 生成 / 子弹 / 响应，属于 Zone 服务命令号，响应命令。
- 906: `ZONE_SCENE_WORLD_COMBAT_SKILL_FIRE_BULLET_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 开火 / 子弹 / 请求，属于 Zone 服务命令号，请求命令。
- 907: `ZONE_SCENE_WORLD_COMBAT_SKILL_FIRE_BULLET_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 开火 / 子弹 / 响应，属于 Zone 服务命令号，响应命令。
- 908: `ZONE_SCENE_WORLD_COMBAT_SKILL_BUFF_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / Buff / 请求，属于 Zone 服务命令号，请求命令。
- 909: `ZONE_SCENE_WORLD_COMBAT_SKILL_BUFF_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / Buff / 响应，属于 Zone 服务命令号，响应命令。
- 910: `ZONE_SCENE_WORLD_COMBAT_SKILL_END_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 结束 / 请求，属于 Zone 服务命令号，请求命令。
- 911: `ZONE_SCENE_WORLD_COMBAT_SKILL_END_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 结束 / 响应，属于 Zone 服务命令号，响应命令。
- 912: `ZONE_SCENE_WORLD_COMBAT_HIT_REQ`；含义：场景 / 大世界 / COMBAT / 命中 / 请求，属于 Zone 服务命令号，请求命令。
- 913: `ZONE_SCENE_WORLD_COMBAT_HIT_RSP`；含义：场景 / 大世界 / COMBAT / 命中 / 响应，属于 Zone 服务命令号，响应命令。
- 914: `ZONE_CANCEL_TASK_RED_POINT_REQ`；含义：取消 / 任务 / 红点 / 点数 / 请求，属于 Zone 服务命令号，请求命令。
- 915: `ZONE_CANCEL_TASK_RED_POINT_RSP`；含义：取消 / 任务 / 红点 / 点数 / 响应，属于 Zone 服务命令号，响应命令。
- 931: `ZONE_SCENE_WORLD_COMBAT_SKILL_JUMP_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 跳跃 / 请求，属于 Zone 服务命令号，请求命令。
- 932: `ZONE_SCENE_WORLD_COMBAT_SKILL_JUMP_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 跳跃 / 响应，属于 Zone 服务命令号，响应命令。
- 933: `ZONE_SCENE_WORLD_COMBAT_SKILL_JUMP_END_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 跳跃 / 结束 / 请求，属于 Zone 服务命令号，请求命令。
- 934: `ZONE_SCENE_WORLD_COMBAT_SKILL_JUMP_END_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 跳跃 / 结束 / 响应，属于 Zone 服务命令号，响应命令。
- 935: `ZONE_SCENE_WORLD_COMBAT_SKILL_RCD_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / RCD / 请求，属于 Zone 服务命令号，请求命令。
- 936: `ZONE_SCENE_WORLD_COMBAT_SKILL_RCD_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / RCD / 响应，属于 Zone 服务命令号，响应命令。
- 937: `ZONE_SCENE_WORLD_COMBAT_SKILL_PET_COLLISION_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 宠物 / 碰撞 / 请求，属于 Zone 服务命令号，请求命令。
- 938: `ZONE_SCENE_WORLD_COMBAT_SKILL_PET_COLLISION_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 宠物 / 碰撞 / 响应，属于 Zone 服务命令号，响应命令。
- 973: `ZONE_SCENE_PLAYER_INTERACT_REQ`；含义：场景 / 玩家 / INTERACT / 请求，属于 Zone 服务命令号，请求命令。
- 974: `ZONE_SCENE_PLAYER_INTERACT_RSP`；含义：场景 / 玩家 / INTERACT / 响应，属于 Zone 服务命令号，响应命令。
- 975: `ZONE_SCENE_REPLY_PLAYER_INTERACT_REQ`；含义：场景 / REPLY / 玩家 / INTERACT / 请求，属于 Zone 服务命令号，请求命令。
- 976: `ZONE_SCENE_REPLY_PLAYER_INTERACT_RSP`；含义：场景 / REPLY / 玩家 / INTERACT / 响应，属于 Zone 服务命令号，响应命令。
- 1004: `ZONE_SCENE_SET_AVATAR_POS_REQ`；含义：场景 / 设置 / 角色 / 位置 / 请求，属于 Zone 服务命令号，请求命令。
- 1005: `ZONE_SCENE_SET_AVATAR_POS_RSP`；含义：场景 / 设置 / 角色 / 位置 / 响应，属于 Zone 服务命令号，响应命令。
- 1024: `ZONE_GET_CAMP_FRUIT_NPC_INFOS_REQ`；含义：获取 / 营地 / 果树 / NPC / INFOS / 请求，属于 Zone 服务命令号，请求命令。
- 1025: `ZONE_GET_CAMP_FRUIT_NPC_INFOS_RSP`；含义：获取 / 营地 / 果树 / NPC / INFOS / 响应，属于 Zone 服务命令号，响应命令。
- 1110: `ZONE_TSS_MESSAGE_CHECK_REQ`；含义：安全检查 / 消息 / 检查 / 请求，属于 Zone 服务命令号，请求命令。
- 1111: `ZONE_TSS_MESSAGE_CHECK_RSP`；含义：安全检查 / 消息 / 检查 / 响应，属于 Zone 服务命令号，响应命令。
- 1151: `ZONE_GET_APPEARANCE_INFO_REQ`；含义：获取 / 外观 / 信息 / 请求，属于 Zone 服务命令号，请求命令。
- 1152: `ZONE_GET_APPEARANCE_INFO_RSP`；含义：获取 / 外观 / 信息 / 响应，属于 Zone 服务命令号，响应命令。
- 1180: `ZONE_GET_HANDBOOK_STAT_REQ`；含义：获取 / 图鉴 / 统计 / 请求，属于 Zone 服务命令号，请求命令。
- 1181: `ZONE_GET_HANDBOOK_STAT_RSP`；含义：获取 / 图鉴 / 统计 / 响应，属于 Zone 服务命令号，响应命令。
- 5105: `ZONE_BATTLE_ENTER_BATTLE_FIELD_REQ`；含义：战斗 / 进入 / 战斗 / FIELD / 请求，属于 Zone 服务命令号，请求命令。
- 5106: `ZONE_BATTLE_ENTER_BATTLE_FIELD_RSP`；含义：战斗 / 进入 / 战斗 / FIELD / 响应，属于 Zone 服务命令号，响应命令。
- 5145: `ZONE_GET_TASK_SWITCH_DATA_REQ`；含义：获取 / 任务 / 开关 / 数据 / 请求，属于 Zone 服务命令号，请求命令。
- 5146: `ZONE_GET_TASK_SWITCH_DATA_RSP`；含义：获取 / 任务 / 开关 / 数据 / 响应，属于 Zone 服务命令号，响应命令。
- 5147: `ZONE_CHANGE_TASK_SWITCH_DATA_REQ`；含义：改变 / 任务 / 开关 / 数据 / 请求，属于 Zone 服务命令号，请求命令。
- 5148: `ZONE_CHANGE_TASK_SWITCH_DATA_RSP`；含义：改变 / 任务 / 开关 / 数据 / 响应，属于 Zone 服务命令号，响应命令。
- 5428: `ZONE_SCENE_HOME_PLANT_CROP_REQ`；含义：场景 / 家园 / PLANT / CROP / 请求，属于 Zone 服务命令号，请求命令。
- 5429: `ZONE_SCENE_HOME_PLANT_CROP_RSP`；含义：场景 / 家园 / PLANT / CROP / 响应，属于 Zone 服务命令号，响应命令。
- 5431: `ZONE_QUERY_SCENE_TASK_STAT_REQ`；含义：查询 / 场景 / 任务 / 统计 / 请求，属于 Zone 服务命令号，请求命令。
- 5432: `ZONE_QUERY_SCENE_TASK_STAT_RSP`；含义：查询 / 场景 / 任务 / 统计 / 响应，属于 Zone 服务命令号，响应命令。
- 5458: `ZONE_START_BADGE_CHALLENGE_REQ`；含义：开始 / 徽章 / 挑战 / 请求，属于 Zone 服务命令号，请求命令。
- 5459: `ZONE_START_BADGE_CHALLENGE_RSP`；含义：开始 / 徽章 / 挑战 / 响应，属于 Zone 服务命令号，响应命令。
- 5460: `ZONE_SELECT_BADGE_CHALLENGE_CARD_REQ`；含义：选择 / 徽章 / 挑战 / 卡牌 / 请求，属于 Zone 服务命令号，请求命令。
- 5461: `ZONE_SELECT_BADGE_CHALLENGE_CARD_RSP`；含义：选择 / 徽章 / 挑战 / 卡牌 / 响应，属于 Zone 服务命令号，响应命令。
- 5462: `ZONE_REFRESH_BADGE_CHALLENGE_CARD_REQ`；含义：刷新 / 徽章 / 挑战 / 卡牌 / 请求，属于 Zone 服务命令号，请求命令。
- 5463: `ZONE_REFRESH_BADGE_CHALLENGE_CARD_RSP`；含义：刷新 / 徽章 / 挑战 / 卡牌 / 响应，属于 Zone 服务命令号，响应命令。
- 5464: `ZONE_COMBINE_BADGE_CHALLENGE_CARD_REQ`；含义：COMBINE / 徽章 / 挑战 / 卡牌 / 请求，属于 Zone 服务命令号，请求命令。
- 5465: `ZONE_COMBINE_BADGE_CHALLENGE_CARD_RSP`；含义：COMBINE / 徽章 / 挑战 / 卡牌 / 响应，属于 Zone 服务命令号，响应命令。
- 5466: `ZONE_FIXED_BADGE_CHALLENGE_CARD_REQ`；含义：FIXED / 徽章 / 挑战 / 卡牌 / 请求，属于 Zone 服务命令号，请求命令。
- 5467: `ZONE_FIXED_BADGE_CHALLENGE_CARD_RSP`；含义：FIXED / 徽章 / 挑战 / 卡牌 / 响应，属于 Zone 服务命令号，响应命令。
- 5468: `ZONE_BADGE_CHALLENGE_SELECT_UPGRADE_REQ`；含义：徽章 / 挑战 / 选择 / UPGRADE / 请求，属于 Zone 服务命令号，请求命令。
- 5469: `ZONE_BADGE_CHALLENGE_SELECT_UPGRADE_RSP`；含义：徽章 / 挑战 / 选择 / UPGRADE / 响应，属于 Zone 服务命令号，响应命令。
- 5470: `ZONE_BADGE_CHALLENGE_ENTER_REQ`；含义：徽章 / 挑战 / 进入 / 请求，属于 Zone 服务命令号，请求命令。
- 5471: `ZONE_BADGE_CHALLENGE_ENTER_RSP`；含义：徽章 / 挑战 / 进入 / 响应，属于 Zone 服务命令号，响应命令。
- 5506: `ZONE_PET_SHARE_PET_TEAM_REQ`；含义：宠物 / SHARE / 宠物 / 队伍 / 请求，属于 Zone 服务命令号，请求命令。
- 5507: `ZONE_PET_SHARE_PET_TEAM_RSP`；含义：宠物 / SHARE / 宠物 / 队伍 / 响应，属于 Zone 服务命令号，响应命令。
- 5521: `ZONE_HOME_DB_TEST_REQ`；含义：家园 / DB / TEST / 请求，属于 Zone 服务命令号，请求命令。
- 5522: `ZONE_HOME_DB_TEST_RSP`；含义：家园 / DB / TEST / 响应，属于 Zone 服务命令号，响应命令。
- 6170: `ZONE_SECONDARY_PASSWORD_CANCEL_FREE_REQ`；含义：二级 / 密码 / 取消 / 免验证 / 请求，属于 Zone 服务命令号，请求命令。
- 6171: `ZONE_SECONDARY_PASSWORD_CANCEL_FREE_RSP`；含义：二级 / 密码 / 取消 / 免验证 / 响应，属于 Zone 服务命令号，响应命令。
- 6172: `ZONE_SECONDARY_PASSWORD_ACTION_CHECK_REQ`；含义：二级 / 密码 / 行为 / 检查 / 请求，属于 Zone 服务命令号，请求命令。
- 6173: `ZONE_SECONDARY_PASSWORD_ACTION_CHECK_RSP`；含义：二级 / 密码 / 行为 / 检查 / 响应，属于 Zone 服务命令号，响应命令。
- 6296: `ZONE_VOD_VIDEO_SIGNATURE_REQ`；含义：点播视频 / 视频 / 签名 / 请求，属于 Zone 服务命令号，请求命令。
- 6297: `ZONE_VOD_VIDEO_SIGNATURE_RSP`；含义：点播视频 / 视频 / 签名 / 响应，属于 Zone 服务命令号，响应命令。
- 6298: `ZONE_PUBLISH_VIDEO_TO_WECHAT_REQ`；含义：发布 / 视频 / 到 / 微信 / 请求，属于 Zone 服务命令号，请求命令。
- 6299: `ZONE_PUBLISH_VIDEO_TO_WECHAT_RSP`；含义：发布 / 视频 / 到 / 微信 / 响应，属于 Zone 服务命令号，响应命令。
- 6306: `ZONE_POPULARITY_VALUE_REWARD_REQ`；含义：POPULARITY / VALUE / 奖励 / 请求，属于 Zone 服务命令号，请求命令。
- 6307: `ZONE_POPULARITY_VALUE_REWARD_RSP`；含义：POPULARITY / VALUE / 奖励 / 响应，属于 Zone 服务命令号，响应命令。
- 6332: `ZONE_CHECK_COLOR_SUIT_STATE_REQ`；含义：检查 / 染色 / 套装 / 状态 / 请求，属于 Zone 服务命令号，请求命令。
- 6333: `ZONE_CHECK_COLOR_SUIT_STATE_RSP`；含义：检查 / 染色 / 套装 / 状态 / 响应，属于 Zone 服务命令号，响应命令。
- 6352: `ZONE_FEED_VIDEO_DEL_UPLOAD_FILE_REQ`；含义：动态 / 视频 / DEL / UPLOAD / FILE / 请求，属于 Zone 服务命令号，请求命令。
- 6353: `ZONE_FEED_VIDEO_DEL_UPLOAD_FILE_RSP`；含义：动态 / 视频 / DEL / UPLOAD / FILE / 响应，属于 Zone 服务命令号，响应命令。
- 6360: `ZONE_GET_CLAIMABLE_GLASS_TINT_REQ`；含义：获取 / 可领取 / 玻璃或镜片 / 染色 / 请求，属于 Zone 服务命令号，请求命令。
- 6361: `ZONE_GET_CLAIMABLE_GLASS_TINT_RSP`；含义：获取 / 可领取 / 玻璃或镜片 / 染色 / 响应，属于 Zone 服务命令号，响应命令。
- 33303: `ZONE_HOME_PET_FOOD_COMPOUND_REQ`；含义：家园 / 宠物 / 食物 / 合成 / 请求，属于 Zone 服务命令号，请求命令。
- 33304: `ZONE_HOME_PET_FOOD_COMPOUND_RSP`；含义：家园 / 宠物 / 食物 / 合成 / 响应，属于 Zone 服务命令号，响应命令。

同一命令号改名：2
- 6388: `ZONE_ACTIVITY_SELECT_TRACK_CONTENTS_REQ` -> `ZONE_ACTIVITY_PHOTO_CONTEST_EVALUATION_NOTIFY`；含义：旧值 活动 / 选择 / 跟踪 / 内容 / 请求，属于 Zone 服务命令号，请求命令。 新值 活动 / 照片 / 比赛 / 评审 / 通知，属于 Zone 服务命令号，通知命令。
- 6389: `ZONE_ACTIVITY_SELECT_TRACK_CONTENTS_RSP` -> `ZONE_ACTIVITY_PHOTO_CONTEST_LIKE_NOTIFY`；含义：旧值 活动 / 选择 / 跟踪 / 内容 / 响应，属于 Zone 服务命令号，响应命令。 新值 活动 / 照片 / 比赛 / 点赞 / 通知，属于 Zone 服务命令号，通知命令。

## Zone 服务消息变化

`zonesvr.proto` 中新增的 `Zone*` message：121
- `ZoneActivityPetTripAddPetReq`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 添加 / 宠物 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPetTripAddPetRsp`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 添加 / 宠物 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPetTripAutoTripReq`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 自动 / 旅行 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPetTripAutoTripRsp`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 自动 / 旅行 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPetTripGetLotteryResultReq`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 获取 / 抽奖 / 结果 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPetTripGetLotteryResultRsp`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 获取 / 抽奖 / 结果 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPetTripGetWishChoiceCountReq`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 获取 / 心愿 / 选择 / 数量 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPetTripGetWishChoiceCountRsp`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 获取 / 心愿 / 选择 / 数量 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPetTripGetWishChoiceCountRsp.WishChoiceCountInfo`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 获取 / 心愿 / 选择 / 数量 / 响应 / 心愿 / 选择 / 数量 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ZoneActivityPetTripReceiveLotteryRewardReq`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 领取 / 抽奖 / 奖励 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPetTripReceiveLotteryRewardRsp`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 领取 / 抽奖 / 奖励 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPetTripSetWishChoiceReq`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 设置 / 心愿 / 选择 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPetTripSetWishChoiceRsp`；含义：Zone 服务 / 活动 / 宠物 / 旅行 / 设置 / 心愿 / 选择 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPhotoContestEvaluationNotify`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 评审 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneActivityPhotoContestEvaluationNotify.PhotoInfo`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 评审 / 通知 / 照片 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ZoneActivityPhotoContestEvaluationReq`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 评审 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPhotoContestEvaluationRsp`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 评审 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPhotoContestHotReq`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 热门 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPhotoContestHotRsp`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 热门 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPhotoContestLikeNotify`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 点赞 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneActivityPhotoContestLikeNotify.PhotoLikeInfo`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 点赞 / 通知 / 照片 / 点赞 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ZoneActivityPhotoContestLikeReq`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 点赞 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPhotoContestLikeRsp`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 点赞 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPhotoContestSubmitReq`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 提交 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPhotoContestSubmitRewardNotify`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 提交 / 奖励 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneActivityPhotoContestSubmitRsp`；含义：Zone 服务 / 活动 / 照片 / 比赛 / 提交 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPopupPlayedReq`；含义：Zone 服务 / 活动 / Popup / Played / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPopupPlayedRsp`；含义：Zone 服务 / 活动 / Popup / Played / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityPredownloadReadyReq`；含义：Zone 服务 / 活动 / Predownload / Ready / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityPredownloadReadyRsp`；含义：Zone 服务 / 活动 / Predownload / Ready / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivityRecallTagSwitchReq`；含义：Zone 服务 / 活动 / 回流 / 标签 / 开关 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivityRecallTagSwitchRsp`；含义：Zone 服务 / 活动 / 回流 / 标签 / 开关 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneActivitySaveRecommendPetTeamReq`；含义：Zone 服务 / 活动 / Save / 推荐 / 宠物 / Team / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneActivitySaveRecommendPetTeamRsp`；含义：Zone 服务 / 活动 / Save / 推荐 / 宠物 / Team / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneAiAttackAbnormalStatusReq`；含义：Zone 服务 / AI / Attack / 异常 / 状态 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneAiAttackAbnormalStatusRsp`；含义：Zone 服务 / AI / Attack / 异常 / 状态 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneAiCoachRecommendLineupNotify`；含义：Zone 服务 / AI / 教练 / 推荐 / 阵容 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneAiCoachRecommendLineupReq`；含义：Zone 服务 / AI / 教练 / 推荐 / 阵容 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneAiCoachRecommendLineupRsp`；含义：Zone 服务 / AI / 教练 / 推荐 / 阵容 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneAiCoachRequestCancelReq`；含义：Zone 服务 / AI / 教练 / Request / 取消 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneAiCoachRequestCancelRsp`；含义：Zone 服务 / AI / 教练 / Request / 取消 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneAiCoachSetStatusReq`；含义：Zone 服务 / AI / 教练 / 设置 / 状态 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneAiCoachSetStatusRsp`；含义：Zone 服务 / AI / 教练 / 设置 / 状态 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneAiCoachWhiteListReq`；含义：Zone 服务 / AI / 教练 / 白 / 列表 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneAiCoachWhiteListRsp`；含义：Zone 服务 / AI / 教练 / 白 / 列表 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneBacktrackPetReq`；含义：Zone 服务 / Backtrack / 宠物 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneBacktrackPetRsp`；含义：Zone 服务 / Backtrack / 宠物 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneBacktrackPetRsp.RewardItem`；含义：Zone 服务 / Backtrack / 宠物 / 响应 / 奖励 / Item，属于协议消息或数据结构，通常表示相关结构或枚举。
- `ZoneBagItemExpireCheckReq`；含义：Zone 服务 / Bag / Item / Expire / Check / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneBagItemExpireCheckRsp`；含义：Zone 服务 / Bag / Item / Expire / Check / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneBagItemExpireConvertReq`；含义：Zone 服务 / Bag / Item / Expire / Convert / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneBagItemExpireConvertRsp`；含义：Zone 服务 / Bag / Item / Expire / Convert / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneDistributeBillNotify`；含义：Zone 服务 / Distribute / Bill / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneGetActivityOptionalPetsReq`；含义：Zone 服务 / 获取 / 活动 / Optional / Pets / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetActivityOptionalPetsRsp`；含义：Zone 服务 / 获取 / 活动 / Optional / Pets / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetAreaIdReq`；含义：Zone 服务 / 获取 / Area / Id / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetAreaIdRsp`；含义：Zone 服务 / 获取 / Area / Id / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetDistributeBillReq`；含义：Zone 服务 / 获取 / Distribute / Bill / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetDistributeBillRsp`；含义：Zone 服务 / 获取 / Distribute / Bill / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetHandbookSeasonAwardReq`；含义：Zone 服务 / 获取 / 图鉴 / 赛季 / Award / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetHandbookSeasonAwardRsp`；含义：Zone 服务 / 获取 / 图鉴 / 赛季 / Award / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetPetInfoByGidReq`；含义：Zone 服务 / 获取 / 宠物 / 信息 / By / Gid / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetPetInfoByGidRsp`；含义：Zone 服务 / 获取 / 宠物 / 信息 / By / Gid / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetRankUserListReq`；含义：Zone 服务 / 获取 / 排行 / User / 列表 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetRankUserListRsp`；含义：Zone 服务 / 获取 / 排行 / User / 列表 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetRankUserReq`；含义：Zone 服务 / 获取 / 排行 / User / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetRankUserRsp`；含义：Zone 服务 / 获取 / 排行 / User / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetSelectAnotherBattlePassThemeFriendsReq`；含义：Zone 服务 / 获取 / 选择 / Another / 战斗 / Pass / Theme / Friends / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetSelectAnotherBattlePassThemeFriendsRsp`；含义：Zone 服务 / 获取 / 选择 / Another / 战斗 / Pass / Theme / Friends / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGmClearDungeonReq`；含义：Zone 服务 / Gm / Clear / Dungeon / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGmClearDungeonRsp`；含义：Zone 服务 / Gm / Clear / Dungeon / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialAbandonChallengeReq`；含义：Zone 服务 / 草系 / 试炼 / Abandon / 挑战 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialAbandonChallengeRsp`；含义：Zone 服务 / 草系 / 试炼 / Abandon / 挑战 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialChallengeDataSyncNotify`；含义：Zone 服务 / 草系 / 试炼 / 挑战 / 数据 / 同步 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneGrassTrialChallengeSettleNotify`；含义：Zone 服务 / 草系 / 试炼 / 挑战 / Settle / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneGrassTrialEnterSceneReq`；含义：Zone 服务 / 草系 / 试炼 / Enter / 场景 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialEnterSceneRsp`；含义：Zone 服务 / 草系 / 试炼 / Enter / 场景 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialGetInfoReq`；含义：Zone 服务 / 草系 / 试炼 / 获取 / 信息 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialGetInfoRsp`；含义：Zone 服务 / 草系 / 试炼 / 获取 / 信息 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialHandleRewardNotify`；含义：Zone 服务 / 草系 / 试炼 / Handle / 奖励 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneGrassTrialHandleRewardReq`；含义：Zone 服务 / 草系 / 试炼 / Handle / 奖励 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialHandleRewardRsp`；含义：Zone 服务 / 草系 / 试炼 / Handle / 奖励 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialNextNodeReq`；含义：Zone 服务 / 草系 / 试炼 / Next / 节点 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialNextNodeRsp`；含义：Zone 服务 / 草系 / 试炼 / Next / 节点 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialNodeRefreshReq`；含义：Zone 服务 / 草系 / 试炼 / 节点 / 刷新 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialNodeRefreshRsp`；含义：Zone 服务 / 草系 / 试炼 / 节点 / 刷新 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialPauseChallengeReq`；含义：Zone 服务 / 草系 / 试炼 / Pause / 挑战 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialPauseChallengeRsp`；含义：Zone 服务 / 草系 / 试炼 / Pause / 挑战 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialResumeChallengeReq`；含义：Zone 服务 / 草系 / 试炼 / Resume / 挑战 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialResumeChallengeRsp`；含义：Zone 服务 / 草系 / 试炼 / Resume / 挑战 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialSelectEventReq`；含义：Zone 服务 / 草系 / 试炼 / 选择 / 事件 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialSelectEventRsp`；含义：Zone 服务 / 草系 / 试炼 / 选择 / 事件 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGrassTrialStartChallengeReq`；含义：Zone 服务 / 草系 / 试炼 / Start / 挑战 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGrassTrialStartChallengeRsp`；含义：Zone 服务 / 草系 / 试炼 / Start / 挑战 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneLlmPetsAvailablePetsReq`；含义：Zone 服务 / Llm / Pets / Available / Pets / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneLlmPetsAvailablePetsRsp`；含义：Zone 服务 / Llm / Pets / Available / Pets / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneLlmPetsBehaviorReportReq`；含义：Zone 服务 / Llm / Pets / Behavior / Report / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneLlmPetsBehaviorReportRsp`；含义：Zone 服务 / Llm / Pets / Behavior / Report / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZonePlayerActivityDropAreaNotify`；含义：Zone 服务 / 玩家 / 活动 / Drop / Area / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZonePlayerBattlePassExpNotify`；含义：Zone 服务 / 玩家 / 战斗 / Pass / 经验 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneQueryBacktrackPetRewardReq`；含义：Zone 服务 / Query / Backtrack / 宠物 / 奖励 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneQueryBacktrackPetRewardRsp`；含义：Zone 服务 / Query / Backtrack / 宠物 / 奖励 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneQueryBacktrackPetRewardRsp.RewardItem`；含义：Zone 服务 / Query / Backtrack / 宠物 / 奖励 / 响应 / 奖励 / Item，属于协议消息或数据结构，通常表示相关结构或枚举。
- `ZoneReceiveActivityRecallBpExpReq`；含义：Zone 服务 / 领取 / 活动 / 回流 / Bp / 经验 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneReceiveActivityRecallBpExpRsp`；含义：Zone 服务 / 领取 / 活动 / 回流 / Bp / 经验 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneReceiveActivityRecallBpLevelRewardReq`；含义：Zone 服务 / 领取 / 活动 / 回流 / Bp / 等级 / 奖励 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneReceiveActivityRecallBpLevelRewardRsp`；含义：Zone 服务 / 领取 / 活动 / 回流 / Bp / 等级 / 奖励 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneReportDistributeReq`；含义：Zone 服务 / Report / Distribute / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneReportDistributeRsp`；含义：Zone 服务 / Report / Distribute / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneRptMonthCardTipsShowReq`；含义：Zone 服务 / Rpt / Month / Card / Tips / Show / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneRptMonthCardTipsShowRsp`；含义：Zone 服务 / Rpt / Month / Card / Tips / Show / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneChangeNpcSizeScaleReq`；含义：Zone 服务 / 场景 / 变化 / NPC / Size / Scale / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneChangeNpcSizeScaleRsp`；含义：Zone 服务 / 场景 / 变化 / NPC / Size / Scale / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneCreateRoleplayPropReq`；含义：Zone 服务 / 场景 / 创建 / 角色扮演 / Prop / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneCreateRoleplayPropRsp`；含义：Zone 服务 / 场景 / 创建 / 角色扮演 / Prop / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneRecycleRoleplayPropReq`；含义：Zone 服务 / 场景 / Recycle / 角色扮演 / Prop / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneRecycleRoleplayPropRsp`；含义：Zone 服务 / 场景 / Recycle / 角色扮演 / Prop / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneThrowCatchFinishReq`；含义：Zone 服务 / 场景 / Throw / 捕获 / Finish / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneThrowCatchFinishRsp`；含义：Zone 服务 / 场景 / Throw / 捕获 / Finish / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneUnlockActivityRecallPaidRewardReq`；含义：Zone 服务 / 解锁 / 活动 / 回流 / 付费 / 奖励 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneUnlockActivityRecallPaidRewardRsp`；含义：Zone 服务 / 解锁 / 活动 / 回流 / 付费 / 奖励 / 响应，属于协议消息或数据结构，通常表示响应消息。

`zonesvr.proto` 中删除的 `Zone*` message：112
- `ZoneBadgeChallengeEnterReq`；含义：Zone 服务 / Badge / 挑战 / Enter / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneBadgeChallengeEnterRsp`；含义：Zone 服务 / Badge / 挑战 / Enter / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneBadgeChallengeSelectUpgradeReq`；含义：Zone 服务 / Badge / 挑战 / 选择 / Upgrade / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneBadgeChallengeSelectUpgradeRsp`；含义：Zone 服务 / Badge / 挑战 / 选择 / Upgrade / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneCancelTaskRedPointReq`；含义：Zone 服务 / 取消 / Task / Red / Point / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneCancelTaskRedPointRsp`；含义：Zone 服务 / 取消 / Task / Red / Point / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneChangeTaskSwitchDataReq`；含义：Zone 服务 / 变化 / Task / 开关 / 数据 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneChangeTaskSwitchDataRsp`；含义：Zone 服务 / 变化 / Task / 开关 / 数据 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneCheckColorSuitStateReq`；含义：Zone 服务 / Check / Color / Suit / 状态 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneCheckColorSuitStateRsp`；含义：Zone 服务 / Check / Color / Suit / 状态 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneClearDungeonReq`；含义：Zone 服务 / Clear / Dungeon / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneClearDungeonRsp`；含义：Zone 服务 / Clear / Dungeon / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneFeedVideoDelUploadFileReq`；含义：Zone 服务 / Feed / Video / Del / Upload / File / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneFeedVideoDelUploadFileRsp`；含义：Zone 服务 / Feed / Video / Del / Upload / File / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneFeedVideoFeedbackReq`；含义：Zone 服务 / Feed / Video / Feedback / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneFeedVideoFeedbackRsp`；含义：Zone 服务 / Feed / Video / Feedback / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetAppearanceInfoReq`；含义：Zone 服务 / 获取 / Appearance / 信息 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetAppearanceInfoRsp`；含义：Zone 服务 / 获取 / Appearance / 信息 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetCampFruitNpcInfosReq`；含义：Zone 服务 / 获取 / Camp / Fruit / NPC / Infos / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetCampFruitNpcInfosRsp`；含义：Zone 服务 / 获取 / Camp / Fruit / NPC / Infos / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetClaimableGlassTintReq`；含义：Zone 服务 / 获取 / Claimable / Glass / Tint / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetClaimableGlassTintRsp`；含义：Zone 服务 / 获取 / Claimable / Glass / Tint / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetHandbookStatReq`；含义：Zone 服务 / 获取 / 图鉴 / Stat / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetHandbookStatRsp`；含义：Zone 服务 / 获取 / 图鉴 / Stat / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetSubTaskTokenTriggeredTaskInfoReq`；含义：Zone 服务 / 获取 / Sub / Task / Token / Triggered / Task / 信息 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetSubTaskTokenTriggeredTaskInfoRsp`；含义：Zone 服务 / 获取 / Sub / Task / Token / Triggered / Task / 信息 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneGetTaskSwitchDataReq`；含义：Zone 服务 / 获取 / Task / 开关 / 数据 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneGetTaskSwitchDataRsp`；含义：Zone 服务 / 获取 / Task / 开关 / 数据 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneHeartbeatReq`；含义：Zone 服务 / Heartbeat / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneHeartbeatRsp`；含义：Zone 服务 / Heartbeat / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneHomePetFoodCompoundReq`；含义：Zone 服务 / Home / 宠物 / Food / Compound / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneHomePetFoodCompoundRsp`；含义：Zone 服务 / Home / 宠物 / Food / Compound / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneJudgePayReq`；含义：Zone 服务 / Judge / Pay / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneJudgePayRsp`；含义：Zone 服务 / Judge / Pay / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneLogoutReq`；含义：Zone 服务 / Logout / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneLogoutRsp`；含义：Zone 服务 / Logout / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneModifyBagListSortReq`；含义：Zone 服务 / Modify / Bag / 列表 / Sort / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneModifyBagListSortRsp`；含义：Zone 服务 / Modify / Bag / 列表 / Sort / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZonePetBasePointAssignReq`；含义：Zone 服务 / 宠物 / 基础 / Point / Assign / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZonePetBasePointAssignReq.BasePointInfo`；含义：Zone 服务 / 宠物 / 基础 / Point / Assign / 请求 / 基础 / Point / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ZonePetBasePointAssignRsp`；含义：Zone 服务 / 宠物 / 基础 / Point / Assign / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZonePetDeleteReq`；含义：Zone 服务 / 宠物 / Delete / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZonePetDeleteRsp`；含义：Zone 服务 / 宠物 / Delete / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZonePetSetFollowReq`；含义：Zone 服务 / 宠物 / 设置 / Follow / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZonePetSetFollowRsp`；含义：Zone 服务 / 宠物 / 设置 / Follow / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZonePetUseBagItemReq`；含义：Zone 服务 / 宠物 / Use / Bag / Item / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZonePetUseBagItemReq.BagItemInfo`；含义：Zone 服务 / 宠物 / Use / Bag / Item / 请求 / Bag / Item / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ZonePetUseBagItemRsp`；含义：Zone 服务 / 宠物 / Use / Bag / Item / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZonePublishVideoToWechatReq`；含义：Zone 服务 / Publish / Video / To / Wechat / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZonePublishVideoToWechatRsp`；含义：Zone 服务 / Publish / Video / To / Wechat / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneQueryAdventureChapterReq`；含义：Zone 服务 / Query / Adventure / Chapter / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneQueryAdventureChapterRsp`；含义：Zone 服务 / Query / Adventure / Chapter / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneQuerySceneTaskStatReq`；含义：Zone 服务 / Query / 场景 / Task / Stat / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneQuerySceneTaskStatRsp`；含义：Zone 服务 / Query / 场景 / Task / Stat / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneRefreshBadgeChallengeCardReq`；含义：Zone 服务 / 刷新 / Badge / 挑战 / Card / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneRefreshBadgeChallengeCardRsp`；含义：Zone 服务 / 刷新 / Badge / 挑战 / Card / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneApplyVisitConfirmReq`；含义：Zone 服务 / 场景 / Apply / Visit / Confirm / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneApplyVisitConfirmRsp`；含义：Zone 服务 / 场景 / Apply / Visit / Confirm / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneApplyVisitListQueryReq`；含义：Zone 服务 / 场景 / Apply / Visit / 列表 / Query / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneApplyVisitListQueryRsp`；含义：Zone 服务 / 场景 / Apply / Visit / 列表 / Query / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneApplyVisitListQueryRsp.ApplyInfo`；含义：Zone 服务 / 场景 / Apply / Visit / 列表 / Query / 响应 / Apply / 信息，属于协议消息或数据结构，通常表示信息结构。
- `ZoneSceneApplyVisitReq`；含义：Zone 服务 / 场景 / Apply / Visit / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneApplyVisitRsp`；含义：Zone 服务 / 场景 / Apply / Visit / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneCastSceneSkillReq`；含义：Zone 服务 / 场景 / Cast / 场景 / Skill / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneCastSceneSkillRsp`；含义：Zone 服务 / 场景 / Cast / 场景 / Skill / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneChangeMoveModeReq`；含义：Zone 服务 / 场景 / 变化 / Move / Mode / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneChangeMoveModeRsp`；含义：Zone 服务 / 场景 / 变化 / Move / Mode / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneGeneralOpReq`；含义：Zone 服务 / 场景 / General / Op / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneGeneralOpRsp`；含义：Zone 服务 / 场景 / General / Op / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneNpcBattleSeriesReq`；含义：Zone 服务 / 场景 / NPC / 战斗 / Series / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneNpcBattleSeriesRsp`；含义：Zone 服务 / 场景 / NPC / 战斗 / Series / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneSetAvatarPosReq`；含义：Zone 服务 / 场景 / 设置 / 玩家角色 / Pos / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneSetAvatarPosRsp`；含义：Zone 服务 / 场景 / 设置 / 玩家角色 / Pos / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneStrongStormNty`；含义：Zone 服务 / 场景 / Strong / Storm / 通知，属于协议消息或数据结构，通常表示通知消息。
- `ZoneSceneThrowCollisionReq`；含义：Zone 服务 / 场景 / Throw / Collision / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneThrowCollisionRsp`；含义：Zone 服务 / 场景 / Throw / Collision / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatHitReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Hit / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatHitRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Hit / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillBuffReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Buff / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillBuffRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Buff / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillCastReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Cast / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillCastRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Cast / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillEndReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / 结束 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillEndRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / 结束 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillFireBulletReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Fire / Bullet / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillFireBulletRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Fire / Bullet / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillJumpEndReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Jump / 结束 / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillJumpEndRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Jump / 结束 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillJumpReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Jump / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillJumpRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Jump / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillPetCollisionReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / 宠物 / Collision / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillPetCollisionRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / 宠物 / Collision / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillRcdReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Rcd / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillRcdRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Rcd / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillSpawnBulletReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Spawn / Bullet / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillSpawnBulletRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Spawn / Bullet / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSceneWorldCombatSkillSpawnNpcReq`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Spawn / NPC / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSceneWorldCombatSkillSpawnNpcRsp`；含义：Zone 服务 / 场景 / 世界 / Combat / Skill / Spawn / NPC / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSecondaryPasswordActionCheckReq`；含义：Zone 服务 / Secondary / Password / 动作 / Check / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSecondaryPasswordActionCheckRsp`；含义：Zone 服务 / Secondary / Password / 动作 / Check / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSecondaryPasswordCancelFreeReq`；含义：Zone 服务 / Secondary / Password / 取消 / Free / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSecondaryPasswordCancelFreeRsp`；含义：Zone 服务 / Secondary / Password / 取消 / Free / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneSyncTempReq`；含义：Zone 服务 / 同步 / Temp / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneSyncTempRsp`；含义：Zone 服务 / 同步 / Temp / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneTaskTraceReq`；含义：Zone 服务 / Task / Trace / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneTaskTraceRsp`；含义：Zone 服务 / Task / Trace / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneTlogReportReq`；含义：Zone 服务 / Tlog / Report / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneTlogReportRsp`；含义：Zone 服务 / Tlog / Report / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneTssMessageCheckReq`；含义：Zone 服务 / Tss / 消息 / Check / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneTssMessageCheckRsp`；含义：Zone 服务 / Tss / 消息 / Check / 响应，属于协议消息或数据结构，通常表示响应消息。
- `ZoneVodVideoSignatureReq`；含义：Zone 服务 / Vod / Video / Signature / 请求，属于协议消息或数据结构，通常表示请求消息。
- `ZoneVodVideoSignatureRsp`；含义：Zone 服务 / Vod / Video / Signature / 响应，属于协议消息或数据结构，通常表示响应消息。

## 共有 message 的字段级变化

字段变化最多的 message：
- `space_data.proto` 中的 `SceneRequiredPlayerInfo`：38 处；含义：场景所需的玩家信息。新版里这个结构被大幅瘦身，旧的大量字段转到了 `OldFlavorSceneRequiredPlayerInfo`。
- `com_action.proto` 中的 `SceneCatchResult`：30 处；含义：场景捕获结果，记录捕获是否成功、捕获球、概率、怪物等级、NPC 信息等。
- `space_action.proto` 中的 `SpaceActionCollection`：13 处；含义：场景/空间行为集合，用来承载各种场景动作通知。
- `com_activity.proto` 中的 `PlayerActivityInfo_ActivityData`：11 处；含义：玩家活动数据集合，包含不同活动模块的玩家进度。
- `space_data.proto` 中的 `ActorData_Avatar`：6 处；含义：玩家角色 Avatar 的场景对象数据。
- `space_data.proto` 中的 `ActorCompData_AvatarMisc`：5 处；含义：玩家角色 Avatar 的杂项组件数据。
- `com_player.proto` 中的 `PlayerSvrDataInfo`：5 处；含义：玩家服务器侧保存的主数据结构。
- `battle_data.proto` 中的 `BattleInsidePetInfo`：5 处；含义：战斗内宠物信息。
- `zonesvr.proto` 中的 `ZoneSecondaryPasswordForceDisableRsp`：4 处；含义：二级密码强制禁用响应。
- `zonesvr.proto` 中的 `ZoneSecondaryPasswordCheckRsp`：4 处；含义：二级密码检查响应。
- `space_data.proto` 中的 `NpcOptionData`：4 处；含义：NPC 交互选项数据。
- `space_data.proto` 中的 `ActorCompData_NpcMisc`：4 处；含义：NPC 杂项组件数据。
- `com_player_data.proto` 中的 `PlayerAdditionalData`：4 处；含义：玩家附加数据。
- `com_player.proto` 中的 `PlayerMiscInfo`：4 处；含义：玩家杂项信息。
- `com_battle.proto` 中的 `CreateBattleInfo`：4 处；含义：创建战斗时使用的战斗信息。
- `space_data.proto` 中的 `CellData_Normal`：3 处；含义：普通场景格子或场景单元数据。
- `space_data.proto` 中的 `ActorInfo_Avatar`：3 处；含义：场景对象 / 信息 / 玩家角色，属于协议消息或数据结构，通常表示相关结构或枚举。
- `com_world_map.proto` 中的 `WorldMapNpcInfo`：3 处；含义：世界 / 地图 / NPC / 信息，属于协议消息或数据结构，通常表示信息结构。
- `com_pet.proto` 中的 `PetBriefInfo`：3 处；含义：宠物 / Brief / 信息，属于协议消息或数据结构，通常表示信息结构。
- `com_match.proto` 中的 `MatchInfo`：3 处；含义：Match / 信息，属于协议消息或数据结构，通常表示信息结构。
- `com_goods.proto` 中的 `GoodsItem`：3 处；含义：Goods / Item，属于协议消息或数据结构，通常表示相关结构或枚举。
- `com_battle.proto` 中的 `BattleNpcInfo`：3 处；含义：战斗 / NPC / 信息，属于协议消息或数据结构，通常表示信息结构。
- `zonesvr.proto` 中的 `ZoneSceneCancelPlayerTransformReq`：2 处；含义：Zone 服务 / 场景 / 取消 / 玩家 / Transform / 请求，属于协议消息或数据结构，通常表示请求消息。
- `space_data.proto` 中的 `PlayerRideStatusParams`：2 处；含义：玩家 / Ride / 状态 / Params，属于协议消息或数据结构，通常表示相关结构或枚举。
- `space_data.proto` 中的 `ActorPartData_NpcBase`：2 处；含义：场景对象 / Part / 数据 / NPC / 基础，属于协议消息或数据结构，通常表示相关结构或枚举。
- `space_data.proto` 中的 `ActorInfo_NpcOptionInfo`：2 处；含义：场景对象 / 信息 / NPC / 选项 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `space_data.proto` 中的 `ActorData_Npc`：2 处；含义：场景对象 / 数据 / NPC，属于协议消息或数据结构，通常表示相关结构或枚举。
- `space_data.proto` 中的 `ActorCompData_Season`：2 处；含义：场景对象 / 组件 / 数据 / 赛季，属于协议消息或数据结构，通常表示相关结构或枚举。
- `space_data.proto` 中的 `ActorCompData_ActionBonus`：2 处；含义：场景对象 / 组件 / 数据 / 动作 / 奖励，属于协议消息或数据结构，通常表示相关结构或枚举。
- `space_action.proto` 中的 `SpaceAct_WorldAttack`：2 处；含义：Space / Act / 世界 / Attack，属于协议消息或数据结构，通常表示相关结构或枚举。
- `com_world_map.proto` 中的 `WorldMapEntry_Npc`：2 处；含义：世界 / 地图 / Entry / NPC，属于协议消息或数据结构，通常表示相关结构或枚举。
- `com_recharge.proto` 中的 `MidasDistriBillInfo`：2 处；含义：Midas / Distri / Bill / 信息，属于协议消息或数据结构，通常表示信息结构。
- `com_player_social_info.proto` 中的 `PlayerSocialAdditionalInfo`：2 处；含义：玩家 / Social / 附加 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `com_pet.proto` 中的 `PetData`：2 处；含义：宠物 / 数据，属于协议消息或数据结构，通常表示数据结构。
- `com_handbook.proto` 中的 `PetHandbook`：2 处；含义：宠物 / 图鉴，属于协议消息或数据结构，通常表示相关结构或枚举。
- `com_battle.proto` 中的 `RankSeasonInfo`：2 处；含义：排行 / 赛季 / 信息，属于协议消息或数据结构，通常表示信息结构。
- `com_battle.proto` 中的 `PlayerPkInfo`：2 处；含义：玩家 / Pk / 信息，属于协议消息或数据结构，通常表示信息结构。
- `com_battle.proto` 中的 `GmBattleNpc`：2 处；含义：Gm / 战斗 / NPC，属于协议消息或数据结构，通常表示相关结构或枚举。
- `com_battle.proto` 中的 `BattlePveInfo`：2 处；含义：战斗 / Pve / 信息，属于协议消息或数据结构，通常表示信息结构。
- `battle_data.proto` 中的 `BattleRoleMagicOpInfo`：2 处；含义：战斗 / Role / 魔法 / Op / 信息，属于协议消息或数据结构，通常表示信息结构。
- `zonesvr_notify.proto` 中的 `ZoneSceneTeleportNotify`：1 处；含义：Zone 服务 / 场景 / Teleport / 通知，属于协议消息或数据结构，通常表示通知消息。
- `zonesvr_notify.proto` 中的 `ZoneRelationshipReqUnlockNotify`：1 处；含义：Zone 服务 / Relationship / 请求 / 解锁 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `zonesvr_notify.proto` 中的 `ZoneFuncBlockingConfsChangeNotify`：1 处；含义：Zone 服务 / Func / Blocking / Confs / 变化 / 通知，属于协议消息或数据结构，通常表示通知消息。
- `zonesvr.proto` 中的 `ZoneSetTaskRecoverAllReq`：1 处；含义：Zone 服务 / 设置 / Task / Recover / All / 请求，属于协议消息或数据结构，通常表示请求消息。
- `zonesvr.proto` 中的 `ZoneSceneNpcControlReq`：1 处；含义：Zone 服务 / 场景 / NPC / Control / 请求，属于协议消息或数据结构，通常表示请求消息。
- `zonesvr.proto` 中的 `ZoneSceneGetFollowInfoRsp`：1 处；含义：Zone 服务 / 场景 / 获取 / Follow / 信息 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `zonesvr.proto` 中的 `ZoneSceneEndThrowRsp`：1 处；含义：Zone 服务 / 场景 / 结束 / Throw / 响应，属于协议消息或数据结构，通常表示响应消息。
- `zonesvr.proto` 中的 `ZoneReceivePlayerActivityDisposableRewardRsp`：1 处；含义：Zone 服务 / 领取 / 玩家 / 活动 / Disposable / 奖励 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `zonesvr.proto` 中的 `ZonePlayerShareInfoRsp`：1 处；含义：Zone 服务 / 玩家 / Share / 信息 / 响应，属于协议消息或数据结构，通常表示响应消息。
- `zonesvr.proto` 中的 `ZonePlayerShareInfoReq`：1 处；含义：Zone 服务 / 玩家 / Share / 信息 / 请求，属于协议消息或数据结构，通常表示请求消息。

### 同一 tag 改名或改类型
- `com_action.proto` 中的 `SceneCatchResult` 字段 1：`bool is_catched` -> `bool catch_success`；含义：旧字段 是否捕获成功。这个旧字段名拼写不太规范，语义上等同于捕获结果。 新字段 是否捕获成功。
- `com_action.proto` 中的 `SceneCatchResult` 字段 2：`int32 probability` -> `int32 ball_conf_id`；含义：旧字段 捕获概率、命中概率或本次判定使用的概率值，具体单位需要结合客户端逻辑确认。 新字段 捕捉球或投掷球的配置 ID。
- `com_action.proto` 中的 `SceneCatchResult` 字段 3：`int32 monter_level` -> `int32 probability`；含义：旧字段 怪物等级。这个旧字段名疑似拼写错误，应该是 monster_level。 新字段 捕获概率、命中概率或本次判定使用的概率值，具体单位需要结合客户端逻辑确认。
- `com_action.proto` 中的 `SceneCatchResult` 字段 4：`Next.MonsterDiffInfo diff_info` -> `bool is_tech_satisfied`；含义：旧字段 怪物差异化信息，例如个体差异、稀有差异或刷新差异。 新字段 是否满足技术捕捉、技巧捕捉或特殊捕捉条件。
- `com_action.proto` 中的 `SceneCatchResult` 字段 10：`int32 caught_weather` -> `uint64 npc_id`；含义：旧字段 捕获发生时的天气 ID 或天气类型。 新字段 NPC 对象 ID。
- `com_action.proto` 中的 `SceneCatchResult` 字段 11：`uint64 caught_ai_status` -> `int32 npc_cfg_id`；含义：旧字段 捕获时 NPC 或怪物的 AI 状态。 新字段 NPC 配置 ID。
- `com_action.proto` 中的 `SceneCatchResult` 字段 12：`int32 gender` -> `uint64 npc_logic_id`；含义：旧字段 性别。 新字段 NPC 逻辑 ID。
- `com_action.proto` 中的 `SceneCatchResult` 字段 13：`bool use_visit_catch_time` -> `uint64 caught_ai_status`；含义：旧字段 是否使用访问场景中的捕获次数或捕获时间规则。 新字段 捕获时 NPC 或怪物的 AI 状态。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 字段 1：`string name` -> `repeated Next.PlayerTag player_tags`；含义：旧字段 名称。 新字段 玩家标签列表。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 字段 2：`int32 lv` -> `uint32 daily_online_time`；含义：旧字段 等级。 新字段 每日在线时长。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 字段 3：`int32 gender` -> `int32 together_starlight_bonus_ratio`；含义：旧字段 性别。 新字段 同行或一起玩法中的星光加成比例。
- `space_action.proto` 中的 `SpaceAct_DeleteThrowNotify` 字段 2：`int32 throw_id` -> `int64 throw_id`；含义：旧字段 投掷物 ID。这里从 int32 变为 int64，说明 ID 范围扩大了。 新字段 投掷物 ID。这里从 int32 变为 int64，说明 ID 范围扩大了。

### 新增字段
- `zonesvr.proto` 中的 `ActivityBriefInfo` 新增字段 5：`bool popup_played`；含义：活动弹窗是否已经播放或展示。
- `space_data.proto` 中的 `ActorCompData_ActionBonus` 新增字段 20：`Next.C2PersistData c2_persist_data`；含义：根据字段名推断为 `c2_persist_data` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `space_data.proto` 中的 `ActorCompData_ActionBonus` 新增字段 109：`uint64 bonus_cnt`；含义：数值字段，通常表示 `bonus_cnt` 对应的 ID、数量、状态或配置值。
- `space_data.proto` 中的 `ActorCompData_AuraMgr` 新增字段 3：`repeated Next.AuraInfo born_aura_infos`；含义：`born_aura_infos` 列表，按字段名可理解为 born / aura / infos 相关数据。
- `space_data.proto` 中的 `ActorCompData_AvatarFriendProxy` 新增字段 1：`Next.AvatarFriendRecommendInfo friend_recommend_info`；含义：好友相关数据。
- `space_data.proto` 中的 `ActorCompData_AvatarMisc` 新增字段 621：`int32 camera_skin_id`；含义：相机皮肤变化数据。
- `space_data.proto` 中的 `ActorCompData_AvatarMisc` 新增字段 622：`repeated int32 unlock_skin_ids`；含义：ID 标识。
- `space_data.proto` 中的 `ActorCompData_AvatarMisc` 新增字段 651：`Next.OfflineOperationConsumeState consume_states`；含义：状态。
- `space_data.proto` 中的 `ActorCompData_AvatarMisc` 新增字段 652：`Next.SceneRequiredPlayerInfo scene_required_player_info`；含义：场景相关数据。
- `space_data.proto` 中的 `ActorCompData_AvatarMisc` 新增字段 653：`Next.TransformStoryFlagData trans_form_story_flag_data`；含义：根据字段名推断为 `trans_form_story_flag_data` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `space_data.proto` 中的 `ActorCompData_Minigame` 新增字段 6：`uint32 mate_uin`；含义：玩家账号 ID。
- `space_data.proto` 中的 `ActorCompData_NpcBattle` 新增字段 2：`repeated uint32 catched_by_uins`；含义：玩家账号 ID。
- `space_data.proto` 中的 `ActorCompData_NpcGuard` 新增字段 6：`repeated Next.NpcGuardLimitData guard_limit_data`；含义：`guard_limit_data` 列表，按字段名可理解为 guard / limit / data 相关数据。
- `space_data.proto` 中的 `ActorCompData_NpcMisc` 新增字段 41：`Next.BoxData box_data`；含义：根据字段名推断为 `box_data` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `space_data.proto` 中的 `ActorCompData_NpcMisc` 新增字段 42：`Next.SeasonPetInfo season_pet_info`；含义：赛季相关数据。
- `space_data.proto` 中的 `ActorCompData_NpcMisc` 新增字段 51：`int32 size_scale`；含义：数值字段，通常表示 `size_scale` 对应的 ID、数量、状态或配置值。
- `space_data.proto` 中的 `ActorCompData_NpcMisc` 新增字段 52：`bool skip_attr_reset`；含义：属性相关数据。
- `space_data.proto` 中的 `ActorCompData_NpcRefresher` 新增字段 25：`int32 high_value_npc_num`；含义：NPC 相关数据。
- `space_data.proto` 中的 `ActorCompData_NpcTrace` 新增字段 3：`int32 fix_data_time`；含义：时间或时间戳。
- `space_data.proto` 中的 `ActorCompData_Season` 新增字段 8：`repeated Next.BossBattleRuleInfo boss_battle_rule_infos`；含义：战斗数据结构。
- `space_data.proto` 中的 `ActorCompData_Season` 新增字段 9：`uint64 next_refresh_word_timestamp`；含义：刷新相关数据。
- `space_data.proto` 中的 `ActorCompData_Thrower` 新增字段 8：`repeated Next.ThrowCatchResultData throw_catch_result_datas`；含义：`throw_catch_result_datas` 列表，按字段名可理解为 throw / catch / result / datas 相关数据。
- `space_data.proto` 中的 `ActorData_Avatar` 新增字段 3：`Next.CompExtendDatas comp_extend_datas`；含义：组件扩展数据。
- `space_data.proto` 中的 `ActorData_Avatar` 新增字段 58：`Next.ActorCompData_CatchBonusCtrl comp_data_catch_bonus_ctrl`；含义：捕捉加成控制数据。
- `space_data.proto` 中的 `ActorData_Avatar` 新增字段 113：`Next.ActorCompData_LlmAgent comp_data_llm_agent`；含义：LLM 宠物或 AI 代理相关数据。
- `space_data.proto` 中的 `ActorData_Avatar` 新增字段 114：`Next.ActorCompData_RoleplayProp comp_data_roleplay_prop`；含义：角色扮演或可持有交互物相关数据。
- `space_data.proto` 中的 `ActorData_Avatar` 新增字段 115：`Next.ActorCompData_AbnormalStatus comp_data_abnormal_status`；含义：异常状态相关数据。
- `space_data.proto` 中的 `ActorData_Avatar` 新增字段 116：`Next.ActorCompData_NpcInfoChange comp_data_npc_info_change`；含义：NPC 相关数据。
- `space_data.proto` 中的 `ActorData_Npc` 新增字段 8：`Next.CompExtendDatas comp_extend_datas`；含义：组件扩展数据。
- `space_data.proto` 中的 `ActorData_Npc` 新增字段 50：`Next.ActorCompData_NpcProp comp_data_npc_prop`；含义：NPC 相关数据。
- `space_data.proto` 中的 `ActorInfo_Aura` 新增字段 13：`repeated uint64 avatar_white_list`；含义：玩家角色或 Avatar 相关数据。
- `space_data.proto` 中的 `ActorInfo_Avatar` 新增字段 39：`Next.ActorInfo_RoleplayPropInfo roleplay_prop_info`；含义：角色扮演或可持有交互物相关数据。
- `space_data.proto` 中的 `ActorInfo_Avatar` 新增字段 40：`Next.ActorInfo_AvatarCamera camera_info`；含义：根据字段名推断为 `camera_info` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `space_data.proto` 中的 `ActorInfo_Avatar` 新增字段 41：`Next.ActorInfo_AvatarAI avatar_ai_info`；含义：玩家角色或 Avatar 相关数据。
- `space_data.proto` 中的 `ActorInfo_AvatarDetailStatus` 新增字段 5：`repeated Next.PlayerTag player_tags`；含义：玩家标签列表。
- `space_data.proto` 中的 `ActorInfo_Npc` 新增字段 24：`Next.ActorInfo_NpcProp npc_prop`；含义：NPC 相关数据。
- `space_data.proto` 中的 `ActorInfo_NpcBase` 新增字段 36：`uint32 owl_sanctuary_content_cfg_id`；含义：ID 标识。
- `space_data.proto` 中的 `ActorInfo_NpcMisc` 新增字段 5：`int32 size_scale`；含义：数值字段，通常表示 `size_scale` 对应的 ID、数量、状态或配置值。
- `space_data.proto` 中的 `ActorInfo_NpcOptionInfo` 新增字段 10：`repeated uint32 whitelist_uins`；含义：玩家账号 ID。
- `space_data.proto` 中的 `ActorInfo_NpcOptionInfo` 新增字段 11：`repeated uint32 blacklist_uins`；含义：玩家账号 ID。
- `space_data.proto` 中的 `ActorPartData_NpcBase` 新增字段 46：`int32 npc_belong_owl_content_id`；含义：NPC 相关数据。
- `space_data.proto` 中的 `ActorPartData_NpcBase` 新增字段 48：`uint64 refresh_batch_id`；含义：刷新相关数据。
- `space_data.proto` 中的 `AvatarNpcRefreshInfo_Refresh` 新增字段 20：`bool rand_rule_reseting`；含义：布尔开关，表示是否满足 `rand_rule_reseting` 对应状态。
- `battle_proto.proto` 中的 `BattleFinishObtainMedalInfo` 新增字段 3：`uint32 normal_task_reward_id`；含义：奖励相关数据。
- `battle_data.proto` 中的 `BattleInsidePetInfo` 新增字段 76：`Next.BoxMonsterInfo box_info`；含义：赛季盒子、宠物盒子或战斗盒子信息。
- `battle_data.proto` 中的 `BattleInsidePetInfo` 新增字段 81：`Next.PetRealInfo real_info`；含义：宠物真实信息或真实属性信息。
- `battle_data.proto` 中的 `BattleInsidePetInfo` 新增字段 85：`int32 buff145_source_pet`；含义：Buff 状态或 Buff 参数。
- `battle_data.proto` 中的 `BattleInsidePetInfo` 新增字段 86：`int32 last_deal_damage_round`；含义：伤害相关数据。
- `battle_data.proto` 中的 `BattleInsidePetInfo` 新增字段 87：`repeated int32 season_attr_add_percent`；含义：赛季相关数据。
- `com_battle.proto` 中的 `BattleMonsterInfo` 新增字段 40：`int32 refresh_type`；含义：刷新相关数据。
- `com_battle.proto` 中的 `BattleNpcInfo` 新增字段 9：`uint32 owner_uin`；含义：玩家账号 ID。
- `com_battle.proto` 中的 `BattleNpcInfo` 新增字段 10：`uint32 npc_refresh_conf_id`；含义：NPC 相关数据。
- `com_battle.proto` 中的 `BattleNpcInfo` 新增字段 11：`Next.SeasonBattleInfo season_add_info`；含义：赛季相关数据。
- `battle_data.proto` 中的 `BattlePerformInfo` 新增字段 52：`Next.BattleBoxShieldBreak box_shield_break`；含义：战斗数据结构。
- `battle_data.proto` 中的 `BattlePetSyncInfo` 新增字段 39：`uint32 max_energy`；含义：数值字段，通常表示 `max_energy` 对应的 ID、数量、状态或配置值。
- `com_battle.proto` 中的 `BattlePveInfo` 新增字段 19：`bool had_season_talent`；含义：赛季相关数据。
- `com_battle.proto` 中的 `BattlePveInfo` 新增字段 20：`uint32 legendary_battle_id`；含义：ID 标识。
- `battle_data.proto` 中的 `BattleRoleMagicOpInfo` 新增字段 10：`bool random_seed_recorded`；含义：布尔开关，表示是否满足 `random_seed_recorded` 对应状态。
- `battle_data.proto` 中的 `BattleRoleMagicOpInfo` 新增字段 11：`uint32 random_seed`；含义：数值字段，通常表示 `random_seed` 对应的 ID、数量、状态或配置值。
- `com_battle.proto` 中的 `BattleSettleInfo` 新增字段 49：`int32 npc_option_id`；含义：NPC 相关数据。
- `battle_data.proto` 中的 `BattleSkillCast` 新增字段 13：`int32 season_id`；含义：赛季相关数据。
- `space_data.proto` 中的 `BonusEventPoolPetCondInfo` 新增字段 3：`repeated Next.BonusContainerCfgRecord bonus_container_record`；含义：AI 相关数据。
- `battle_buff_data.proto` 中的 `BuffData_64` 新增字段 2：`int32 history_start_index`；含义：数值字段，通常表示 `history_start_index` 对应的 ID、数量、状态或配置值。
- `battle_buff_data.proto` 中的 `BuffData_93` 新增字段 3：`uint32 selected_buffbase_id`；含义：Buff 状态或 Buff 参数。
- `space_data.proto` 中的 `CellCompData_HomePet` 新增字段 9：`int32 lay_egg_seed`；含义：数值字段，通常表示 `lay_egg_seed` 对应的 ID、数量、状态或配置值。
- `space_data.proto` 中的 `CellData_Normal` 新增字段 2：`Next.CompExtendDatas comp_extend_datas`；含义：组件扩展数据。
- `space_data.proto` 中的 `CellData_Normal` 新增字段 46：`Next.CellCompData_AreaDetector comp_data_area_detector`；含义：根据字段名推断为 `comp_data_area_detector` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `com_relation.proto` 中的 `ChatSessionInfo.FriendSessionInfo` 新增字段 15：`Next.FriendPositionInfo pos_info`；含义：位置坐标。
- `com_scene_ai.proto` 中的 `ClientAiCommandInfo` 新增字段 5：`string string_param`；含义：文本或二进制内容，表示 `string_param` 对应的数据。
- `space_data.proto` 中的 `ClientOperation` 新增字段 18：`Next.TakePhotoEmojiPoseSyncInfo photo_info`；含义：根据字段名推断为 `photo_info` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `com_account.proto` 中的 `ClientTokenInfo` 新增字段 6：`bytes wg_login_info`；含义：文本或二进制内容，表示 `wg_login_info` 对应的数据。
- `battle_buff_data.proto` 中的 `CommonBuffData` 新增字段 6：`Next.BuffData_146_Common b146`；含义：根据字段名推断为 `b146` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `com_battle.proto` 中的 `CreateBattleInfo` 新增字段 43：`Next.SeasonBattleInfo season_add_info`；含义：赛季相关数据。
- `com_battle.proto` 中的 `CreateBattleInfo` 新增字段 44：`repeated uint32 visit_uins`；含义：玩家账号 ID。
- `com_battle.proto` 中的 `CreateBattleInfo` 新增字段 120：`repeated Next.GmBattleNpc dynamic_attacker_npcs`；含义：NPC 相关数据。
- `com_battle.proto` 中的 `CreateBattleInfo` 新增字段 121：`Next.GrassBadgeTrialInfo grass_trial_info`；含义：草系试炼相关数据。
- `battle_data.proto` 中的 `EnhanceEffectInfo` 新增字段 4：`int32 add_round`；含义：回合相关数据。
- `com_pet_team.proto` 中的 `FriendPetTeamBufferFriendInfo` 新增字段 4：`bytes note`；含义：文本或二进制内容，表示 `note` 对应的数据。
- `friend_data.proto` 中的 `FriendRoleInfo` 新增字段 37：`repeated Next.PlayerTag tags`；含义：玩家数据结构。
- `com_appearance.proto` 中的 `GlassTintChange` 新增字段 3：`uint32 show_gid`；含义：ID 标识。
- `com_battle.proto` 中的 `GmBattleNpc` 新增字段 3：`int32 fashion_id`；含义：时装相关数据。
- `com_battle.proto` 中的 `GmBattleNpc` 新增字段 4：`int32 sex`；含义：数值字段，通常表示 `sex` 对应的 ID、数量、状态或配置值。
- `com_goods.proto` 中的 `GoodsItem` 新增字段 22：`int32 npc_refresh_type`；含义：NPC 相关数据。
- `com_goods.proto` 中的 `GoodsItem` 新增字段 23：`uint64 npc_obj_id`；含义：NPC 相关数据。
- `com_goods.proto` 中的 `GoodsItem` 新增字段 24：`uint64 battle_id`；含义：ID 标识。
- `com_home.proto` 中的 `HomePetBriefInfo` 新增字段 5：`int64 predicted_egg_time`；含义：时间或时间戳。
- `com_battle.proto` 中的 `InnerBattlePetDisplay` 新增字段 11：`uint32 ball_id`；含义：ID 标识。
- `battle_data.proto` 中的 `LegendaryBattleInfo` 新增字段 3：`uint32 legendary_battle_id`；含义：ID 标识。
- `mail_data.proto` 中的 `MailInfo` 新增字段 19：`uint32 mail_sub_type`；含义：AI 相关数据。
- `com_mail.proto` 中的 `MailRecvBrief` 新增字段 13：`uint32 mail_sub_type`；含义：AI 相关数据。
- `com_match.proto` 中的 `MatchInfo` 新增字段 24：`int32 welfare_team_cnt`；含义：数值字段，通常表示 `welfare_team_cnt` 对应的 ID、数量、状态或配置值。
- `com_match.proto` 中的 `MatchInfo` 新增字段 25：`Next.Pvp_MuteGroups self_mute_groups`；含义：根据字段名推断为 `self_mute_groups` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `com_match.proto` 中的 `MatchInfo` 新增字段 26：`repeated Next.Pvp_MuteGroups same_team_mute_groups`；含义：`same_team_mute_groups` 列表，按字段名可理解为 same / team / mute / groups 相关数据。
- `com_match.proto` 中的 `MatchSuccInfo` 新增字段 14：`int32 welfare_team_cnt`；含义：数值字段，通常表示 `welfare_team_cnt` 对应的 ID、数量、状态或配置值。
- `com_recharge.proto` 中的 `MidasDistriBillInfo` 新增字段 3：`uint32 goods_id`；含义：ID 标识。
- `com_recharge.proto` 中的 `MidasDistriBillInfo` 新增字段 4：`uint32 create_time`；含义：时间或时间戳。
- `com_shop.proto` 中的 `MonthCardData` 新增字段 9：`uint32 daily_tips_show`；含义：AI 相关数据。
- `space_data.proto` 中的 `NpcOptionData` 新增字段 12：`repeated uint32 white_list_uins`；含义：玩家账号 ID。
- `space_data.proto` 中的 `NpcOptionData` 新增字段 13：`repeated uint32 black_list_uins`；含义：玩家账号 ID。
- `space_data.proto` 中的 `NpcOptionData` 新增字段 33：`Next.NpcOptionData_CooldownInfo cooldown_info`；含义：根据字段名推断为 `cooldown_info` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `space_data.proto` 中的 `NpcOptionData` 新增字段 34：`Next.NpcOptionStashExtraData stash_extra_data`；含义：根据字段名推断为 `stash_extra_data` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `battle_proto.proto` 中的 `ObserverPvpScoreRecord` 新增字段 4：`int32 get_pvp_score`；含义：数值字段，通常表示 `get_pvp_score` 对应的 ID、数量、状态或配置值。
- `space_data.proto` 中的 `OwlContentMetaData` 新增字段 7：`uint32 owl_sanctuary_habitat_id`；含义：ID 标识。
- `com_pet.proto` 中的 `PetBackpackInfo` 新增字段 6：`repeated dataconfig.PetBoxTidyRuleType tidy_rules`；含义：ID 标识。
- `com_pet.proto` 中的 `PetBacktrack` 新增字段 10：`Next.PetBacktrackShowInfo show_info`；含义：宠物数据结构。
- `com_pet.proto` 中的 `PetBox` 新增字段 6：`bool lock`；含义：布尔开关，表示是否满足 `lock` 对应状态。
- `com_pet.proto` 中的 `PetBriefInfo` 新增字段 56：`uint32 changed_nature_pos_attr_type`；含义：属性相关数据。
- `com_pet.proto` 中的 `PetBriefInfo` 新增字段 57：`uint32 changed_nature_neg_attr_type`；含义：属性相关数据。
- `com_pet.proto` 中的 `PetBriefInfo` 新增字段 95：`Next.PetNatureAttrChangeWay nature_attr_change_way`；含义：属性相关数据。
- `com_pet.proto` 中的 `PetData` 新增字段 101：`Next.SeasonBattleInfo season_add_info`；含义：赛季相关数据。
- `com_pet.proto` 中的 `PetData` 新增字段 104：`Next.PetLLMNatureTagInfo llm_nature_tag`；含义：LLM 宠物或 AI 代理相关数据。
- `com_pet_egg.proto` 中的 `PetEggBrief` 新增字段 24：`uint32 talent_rank`；含义：排行榜相关数据。
- `com_handbook.proto` 中的 `PetHandbook` 新增字段 12：`repeated Next.PetHandbookSeasonInfo season_info`；含义：赛季相关数据。
- `com_handbook.proto` 中的 `PetHandbook` 新增字段 13：`int32 belong_area_version`；含义：版本号。
- `com_pet.proto` 中的 `PetKeyExperience` 新增字段 7：`Next.PetBackTrackRecordInfo backtrack_record_info`；含义：宠物数据结构。
- `com_pet_medal.proto` 中的 `PetMedal` 新增字段 4：`uint32 trigger_pet_gid`；含义：宠物相关数据。
- `com_pet.proto` 中的 `PetSceneInfo` 新增字段 7：`Next.PetLLMNatureTagInfo llm_nature_tag`；含义：LLM 宠物或 AI 代理相关数据。
- `com_pet_skill.proto` 中的 `PetSkillData` 新增字段 6：`int32 season_id`；含义：赛季相关数据。
- `battle_data.proto` 中的 `PetSkillRoundData` 新增字段 68：`int32 season_id`；含义：赛季相关数据。
- `com_pet_team.proto` 中的 `PetTeam` 新增字段 12：`repeated uint32 mirror_boss_evo_items`；含义：道具相关数据。
- `com_activity.proto` 中的 `PlayerActivityInfo_ActivityData` 新增字段 40：`Next.PlayerActivityInfo_ActivityPhotoContest photo_contest_data`；含义：摄影或照片比赛相关数据。
- `com_activity.proto` 中的 `PlayerActivityInfo_ActivityData` 新增字段 41：`bool popup_played`；含义：活动弹窗是否已经播放或展示。
- `com_activity.proto` 中的 `PlayerActivityInfo_ActivityData` 新增字段 42：`Next.PlayerActivityInfo_ActivityGlobalChallengeData global_challenge_data`；含义：全服或全局挑战相关数据。
- `com_activity.proto` 中的 `PlayerActivityInfo_ActivityData` 新增字段 43：`Next.PlayerActivityInfo_ActivitySignRewardData sign_reward_data`；含义：签到奖励相关数据。
- `com_activity.proto` 中的 `PlayerActivityInfo_ActivityData` 新增字段 44：`Next.PlayerActivityInfo_ActivityWeekendChallengeData weekend_challenge_data`；含义：周末挑战相关数据。
- `com_activity.proto` 中的 `PlayerActivityInfo_ActivityData` 新增字段 45：`Next.PlayerActivityInfo_ActivityPetTripData pet_trip_data`；含义：宠物旅行相关数据。
- `com_activity.proto` 中的 `PlayerActivityInfo_ActivityData` 新增字段 46：`Next.PlayerActivityInfo_ActivityRecallStarlightData recall_starlight_data`；含义：回流活动相关数据。
- `com_activity.proto` 中的 `PlayerActivityInfo_ActivityData` 新增字段 47：`Next.PlayerActivityInfo_ActivityRecallBPData recall_bp_data`；含义：回流活动相关数据。
- `com_activity.proto` 中的 `PlayerActivityInfo_ActivityData` 新增字段 48：`Next.PlayerActivityInfo_ActivityRecallData recall_data`；含义：回流活动相关数据。
- `com_activity.proto` 中的 `PlayerActivityInfo_ActivityData` 新增字段 50：`Next.PlayerActivityInfo_ActivityBaseMixData base_mix_data`；含义：基础混合活动相关数据。
- `com_activity.proto` 中的 `PlayerActivityInfo_ActivityData` 新增字段 51：`Next.PlayerActivityInfo_PreDownloadData pre_download_data`；含义：预下载活动数据。
- `com_activity.proto` 中的 `PlayerActivityInfo_ActivityInviteRegisterData` 新增字段 2：`uint32 inviter_uin`；含义：玩家账号 ID。
- `com_activity.proto` 中的 `PlayerActivityInfo_ActivityPartData` 新增字段 6：`uint32 last_refresh_time`；含义：刷新相关数据。
- `com_player_data.proto` 中的 `PlayerAdditionalData` 新增字段 20：`repeated Next.PlayerTag player_tags`；含义：玩家标签列表。
- `com_player_data.proto` 中的 `PlayerAdditionalData` 新增字段 21：`int32 together_starlight_bonus_ratio`；含义：同行或一起玩法中的星光加成比例。
- `com_player_data.proto` 中的 `PlayerAdditionalData` 新增字段 22：`bytes plat_nick_name`；含义：文本或二进制内容，表示 `plat_nick_name` 对应的数据。
- `com_player_data.proto` 中的 `PlayerAdditionalData` 新增字段 23：`bytes plat_avatar_url`；含义：玩家角色或 Avatar 相关数据。
- `com_appearance.proto` 中的 `PlayerAppearanceInfo` 新增字段 4：`uint32 patch_version`；含义：版本号。
- `com_player.proto` 中的 `PlayerBagInfo` 新增字段 16：`Next.BagItemExpireList bag_item_expire_list`；含义：背包相关数据。
- `com_player.proto` 中的 `PlayerBattleData_ObserveBattleData` 新增字段 4：`uint64 observe_start_time`；含义：时间或时间戳。
- `com_player_data.proto` 中的 `PlayerBusinessCardInfo` 新增字段 9：`string cur_card_md5`；含义：文本或二进制内容，表示 `cur_card_md5` 对应的数据。
- `com_player_data.proto` 中的 `PlayerCardBriefInfo` 新增字段 13：`Next.PlayerCardBriefInfo_PetInfo card_pet_info`；含义：宠物相关数据。
- `com_player_data.proto` 中的 `PlayerHomeBriefInfo` 新增字段 11：`Next.HomeAccessInfo access_info`；含义：根据字段名推断为 `access_info` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `com_player.proto` 中的 `PlayerMiscInfo` 新增字段 26：`repeated Next.ActivityPetTripLotteryRecord activity_lottery_records`；含义：活动相关数据。
- `com_player.proto` 中的 `PlayerMiscInfo` 新增字段 27：`Next.OfflineOperationConsumeState offline_operation_consume_state`；含义：状态。
- `com_player.proto` 中的 `PlayerMiscInfo` 新增字段 28：`bool has_aicoach_shown_notify`；含义：AI 相关数据。
- `com_player.proto` 中的 `PlayerMiscInfo` 新增字段 29：`Next.SeasonCatchRewardInfo season_catch_reward_info`；含义：赛季相关数据。
- `com_player.proto` 中的 `PlayerPetInfo` 新增字段 37：`Next.PetReportBriefInfo report_brief_info`；含义：宠物数据结构。
- `com_battle.proto` 中的 `PlayerPkInfo` 新增字段 38：`int32 light_pk`；含义：数值字段，通常表示 `light_pk` 对应的 ID、数量、状态或配置值。
- `com_battle.proto` 中的 `PlayerPkInfo` 新增字段 39：`int32 light_pk_option_id`；含义：ID 标识。
- `space_data.proto` 中的 `PlayerRideSkillStatusParams` 新增字段 4：`Next.CircusPetParams circus_pet_params`；含义：宠物相关数据。
- `space_data.proto` 中的 `PlayerRideStatusParams` 新增字段 21：`Next.ResonanceInfo resonance_info`；含义：根据字段名推断为 `resonance_info` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `space_data.proto` 中的 `PlayerRideStatusParams` 新增字段 22：`int32 option_id`；含义：ID 标识。
- `space_data.proto` 中的 `PlayerRolePlayStatusParams` 新增字段 13：`int32 ball_id`；含义：ID 标识。
- `com_player_data.proto` 中的 `PlayerSettingBriefInfo` 新增字段 5：`Next.AiCoachStatus ai_coach_status`；含义：AI 相关数据。
- `com_player_social_info.proto` 中的 `PlayerSocialAdditionalInfo` 新增字段 5：`repeated Next.PlayerTag player_tags`；含义：玩家标签列表。
- `com_player_social_info.proto` 中的 `PlayerSocialAdditionalInfo` 新增字段 6：`Next.PlayerBattlePassSocialInfo battle_pass_info`；含义：战令或通行证相关数据。
- `com_player.proto` 中的 `PlayerSvrDataInfo` 新增字段 97：`repeated Next.PlayerNpcLotteryData npc_lottery_data`；含义：NPC 抽奖或随机奖励数据。
- `com_player.proto` 中的 `PlayerSvrDataInfo` 新增字段 98：`Next.BadgeTrialData badge_trial_data`；含义：徽章试炼相关数据。
- `com_player.proto` 中的 `PlayerSvrDataInfo` 新增字段 99：`Next.IdipMailSerialList idip_mail_serials`；含义：IDIP 邮件流水或邮件序列数据。
- `com_player.proto` 中的 `PlayerSvrDataInfo` 新增字段 100：`Next.OptReWardNumList opt_reward_info`；含义：可选奖励或运营奖励次数数据。
- `com_player.proto` 中的 `PlayerSvrDataInfo` 新增字段 105：`uint32 flow_gid`；含义：流程全局 ID 或当前流程标识。
- `com_battle.proto` 中的 `PvpFightHis` 新增字段 13：`uint32 season_id`；含义：赛季相关数据。
- `com_battle.proto` 中的 `PvpModeCtl` 新增字段 13：`int32 light_pk`；含义：数值字段，通常表示 `light_pk` 对应的 ID、数量、状态或配置值。
- `com_battle.proto` 中的 `PvpRecord` 新增字段 54：`repeated Next.Pvp_MuteGroups same_team_mute_groups`；含义：`same_team_mute_groups` 列表，按字段名可理解为 same / team / mute / groups 相关数据。
- `battle_proto.proto` 中的 `PvpScoreRecord` 新增字段 17：`int32 raw_score`；含义：数值字段，通常表示 `raw_score` 对应的 ID、数量、状态或配置值。
- `com_battle.proto` 中的 `RankSeasonInfo` 新增字段 8：`int32 rank_order`；含义：排行榜相关数据。
- `com_battle.proto` 中的 `RankSeasonInfo` 新增字段 9：`uint32 master_score`；含义：数值字段，通常表示 `master_score` 对应的 ID、数量、状态或配置值。
- `com_home.proto` 中的 `RoomFurnitureDetails` 新增字段 8：`repeated uint64 dynamic_npc_ids`；含义：NPC 相关数据。
- `com_pet.proto` 中的 `SceneBasePetData` 新增字段 28：`Next.PetLLMNatureTagInfo llm_nature_tag`；含义：LLM 宠物或 AI 代理相关数据。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 14：`int32 caught_ai_behavior`；含义：AI 相关数据。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 15：`bool is_detected`；含义：布尔开关，表示是否满足 `is_detected` 对应状态。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 16：`bool is_back_stab`；含义：布尔开关，表示是否满足 `is_back_stab` 对应状态。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 17：`int32 refresh_source`；含义：刷新相关数据。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 20：`Next.Point avatar_pt`；含义：玩家角色或 Avatar 相关数据。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 21：`bool is_visiting`；含义：布尔开关，表示是否满足 `is_visiting` 对应状态。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 22：`bool is_visiting_owner`；含义：布尔开关，表示是否满足 `is_visiting_owner` 对应状态。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 23：`string visit_owner_name`；含义：文本或二进制内容，表示 `visit_owner_name` 对应的数据。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 24：`uint32 caught_camp`；含义：数值字段，通常表示 `caught_camp` 对应的 ID、数量、状态或配置值。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 25：`int32 caught_weather`；含义：捕获发生时的天气 ID 或天气类型。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 26：`bool is_throw_together`；含义：布尔开关，表示是否满足 `is_throw_together` 对应状态。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 31：`Next.MonsterDiffInfo diff_info`；含义：怪物差异化信息，例如个体差异、稀有差异或刷新差异。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 32：`int32 monster_level`；含义：怪物等级。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 33：`int32 monster_id`；含义：ID 标识。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 34：`int32 gender`；含义：性别。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 35：`int32 pet_base_id`；含义：宠物相关数据。
- `com_action.proto` 中的 `SceneCatchResult` 新增字段 36：`Next.SeasonPetInfo season_pet_info`；含义：赛季相关数据。
- `space_data.proto` 中的 `SceneData_Normal` 新增字段 2：`Next.CompExtendDatas comp_extend_datas`；含义：组件扩展数据。
- `space_data.proto` 中的 `SceneMgrData_Normal` 新增字段 2：`Next.CompExtendDatas comp_extend_datas`；含义：组件扩展数据。
- `com_misc.proto` 中的 `SceneSeasonInfo` 新增字段 4：`bool is_open`；含义：布尔开关，表示是否满足 `is_open` 对应状态。
- `com_activity.proto` 中的 `SeasonInfo` 新增字段 10：`uint32 season_legendary_id`；含义：赛季相关数据。
- `com_activity.proto` 中的 `SeasonPlayerGrowth` 新增字段 4：`uint32 new_pet_conf_id`；含义：宠物相关数据。
- `battle_data.proto` 中的 `SkillCastRecord` 新增字段 22：`int32 season_id`；含义：赛季相关数据。
- `space_action.proto` 中的 `SpaceAct_IdleSkill` 新增字段 8：`int32 gid`；含义：ID 标识。
- `space_action.proto` 中的 `SpaceAct_NpcOptionInfoChange` 新增字段 11：`bool is_cancel`；含义：布尔开关，表示是否满足 `is_cancel` 对应状态。
- `space_action.proto` 中的 `SpaceAct_WorldAttack` 新增字段 15：`int32 abnormal_type`；含义：类型。
- `space_action.proto` 中的 `SpaceAct_WorldAttack` 新增字段 16：`float abnormal_duration`；含义：浮点数值，通常表示 `abnormal_duration` 对应的比例、速度、时间或参数值。
- `space_action.proto` 中的 `SpaceActionCollection` 新增字段 114：`Next.SpaceAct_AIMutualPerformStateChanged mutual_perform_state_changed`；含义：互相表演或双人互动状态数据。
- `space_action.proto` 中的 `SpaceActionCollection` 新增字段 266：`Next.SpaceAct_PlayChatBubble play_chat_buble`；含义：根据字段名推断为 `play_chat_buble` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `space_action.proto` 中的 `SpaceActionCollection` 新增字段 267：`Next.SpaceAct_PlayerTagsChange player_tags_change`；含义：玩家标签变化数据。
- `space_action.proto` 中的 `SpaceActionCollection` 新增字段 268：`Next.SpaceAct_AbnormalStatusChangeNtf abnormal_status_change_ntf`；含义：异常状态相关数据。
- `space_action.proto` 中的 `SpaceActionCollection` 新增字段 269：`Next.SpaceAct_BonusCatchLimitTips bonus_catch_limit_tips`；含义：奖励捕捉或额外捕捉提示数据。
- `space_action.proto` 中的 `SpaceActionCollection` 新增字段 500：`Next.SpaceAct_LLM_PETS_QueryPets llm_pets_query_pets`；含义：宠物相关数据。
- `space_action.proto` 中的 `SpaceActionCollection` 新增字段 501：`Next.SpaceAct_LLM_PETS_BehaviorNotify llm_pets_behavior_notify`；含义：宠物相关数据。
- `space_action.proto` 中的 `SpaceActionCollection` 新增字段 502：`Next.SpaceAct_LLMDebug llm_debug`；含义：LLM 宠物或 AI 代理相关数据。
- `space_action.proto` 中的 `SpaceActionCollection` 新增字段 510：`Next.SpaceAct_NpcSizeScaleChange npc_size_scale_change`；含义：NPC 相关数据。
- `space_action.proto` 中的 `SpaceActionCollection` 新增字段 513：`Next.SpaceAct_CameraSkinChange camera_skin_change`；含义：相机皮肤变化数据。
- `space_action.proto` 中的 `SpaceActionCollection` 新增字段 515：`Next.SpaceAct_NpcMutationInfoChange npc_mutation_info_change`；含义：NPC 相关数据。
- `space_action.proto` 中的 `SpaceActionCollection` 新增字段 601：`Next.SpaceAct_RoleplayHoldInfoChgNtf roleplay_hold_info_chg_ntf`；含义：角色扮演或可持有交互物相关数据。
- `space_action.proto` 中的 `SpaceActionCollection` 新增字段 602：`Next.SpaceAct_OptionBlackOrWhiteListUinsChgNtf option_b_or_w_list_uins_chg_ntf`；含义：选项黑白名单账号变化数据。
- `com_battle.proto` 中的 `SpecBattleDifficultyInfo` 新增字段 3：`repeated Next.SpecBattleDifficultyItemInfo won_difficults`；含义：战斗数据结构。
- `com_task.proto` 中的 `TaskContentItem` 新增字段 9：`uint32 reward_cnt`；含义：奖励相关数据。
- `com_action.proto` 中的 `ThrowTargetNpcInfo` 新增字段 11：`int32 npc_refresh_type`；含义：NPC 相关数据。
- `com_world_map.proto` 中的 `WorldMapNpcInfo` 新增字段 12：`Next.GlassInfo glass_info`；含义：根据字段名推断为 `glass_info` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `com_world_map.proto` 中的 `WorldMapNpcInfo` 新增字段 13：`int32 mutation_type`；含义：类型。
- `com_world_map.proto` 中的 `WorldMapNpcInfo` 新增字段 14：`int64 npc_born_time`；含义：NPC 相关数据。
- `zonesvr.proto` 中的 `ZoneAddPetRecordReq` 新增字段 3：`uint64 npc_actor_id`；含义：NPC 相关数据。
- `battle_proto.proto` 中的 `ZoneBattlePlayerExitReq` 新增字段 1：`uint64 battle_id`；含义：ID 标识。
- `battle_proto.proto` 中的 `ZoneBattlePlayerRunawayReq` 新增字段 1：`int32 runaway_type`；含义：类型。
- `zonesvr.proto` 中的 `ZoneBusinessCardUploadSuccessReq` 新增字段 2：`string photo_md5`；含义：文本或二进制内容，表示 `photo_md5` 对应的数据。
- `zonesvr.proto` 中的 `ZoneBuyGoodsByMidasRsp` 新增字段 10：`uint32 create_time`；含义：时间或时间戳。
- `zonesvr.proto` 中的 `ZoneChatGetChatMessageRsp` 新增字段 6：`bool all_msg_fetched`；含义：布尔开关，表示是否满足 `all_msg_fetched` 对应状态。
- `zonesvr.proto` 中的 `ZoneEnterSceneRsp` 新增字段 7：`uint32 online_visiting_owner`；含义：数值字段，通常表示 `online_visiting_owner` 对应的 ID、数量、状态或配置值。
- `zonesvr.proto` 中的 `ZoneFeedMagicCreateReq` 新增字段 6：`uint32 sub_type`；含义：类型。
- `zonesvr.proto` 中的 `ZoneFriendGetRecommendFriendListReq` 新增字段 2：`uint32 source`；含义：来源类型或来源 ID。
- `zonesvr.proto` 中的 `ZoneFriendSearchPlayerRsp` 新增字段 6：`bool can_be_add_friend`；含义：好友相关数据。
- `zonesvr_notify.proto` 中的 `ZoneFuncBlockingConfsChangeNotify` 新增字段 2：`bool is_audit`；含义：布尔开关，表示是否满足 `is_audit` 对应状态。
- `zonesvr.proto` 中的 `ZoneGetPlayerCardBriefInfoRsp` 新增字段 12：`uint64 topic_point`；含义：点位或坐标点。
- `zone_gm.proto` 中的 `ZoneGmCreateBattleReq` 新增字段 19：`repeated Next.GmBattleNpc dynamic_attacker_npcs`；含义：NPC 相关数据。
- `zone_gm.proto` 中的 `ZoneGmQueryBattleFieldReq` 新增字段 5：`int32 data_layer`；含义：数值字段，通常表示 `data_layer` 对应的 ID、数量、状态或配置值。
- `zonesvr.proto` 中的 `ZoneLightSeasonTalentPointReq` 新增字段 3：`uint32 new_pet_conf_id`；含义：宠物相关数据。
- `zonesvr.proto` 中的 `ZoneLoginRsp` 新增字段 10：`Next.WegameAuthResult wg_auth_result`；含义：根据字段名推断为 `wg_auth_result` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `feed_data.proto` 中的 `ZoneMagicFeedInfo` 新增字段 19：`uint32 sub_type`；含义：类型。
- `zone_mail.proto` 中的 `ZoneMailGetAttachmentRsp.GetFailGoodsInfo` 新增字段 3：`uint32 pet_base_id`；含义：宠物相关数据。
- `zonesvr.proto` 中的 `ZoneOpenRelationshipTreeRsp.RelationshipTreePeerInfo` 新增字段 11：`repeated Next.PlayerTag tags`；含义：玩家数据结构。
- `zonesvr.proto` 中的 `ZonePetBoxSetMarkTypeReq` 新增字段 4：`bool lock`；含义：布尔开关，表示是否满足 `lock` 对应状态。
- `zonesvr.proto` 中的 `ZonePetBoxSetMarkTypeRsp` 新增字段 5：`bool lock`；含义：布尔开关，表示是否满足 `lock` 对应状态。
- `zonesvr.proto` 中的 `ZonePetBoxTidyReq` 新增字段 2：`repeated dataconfig.PetBoxTidyRuleType tidy_rules`；含义：ID 标识。
- `zonesvr.proto` 中的 `ZonePetBoxTidyRsp` 新增字段 4：`repeated dataconfig.PetBoxTidyRuleType tidy_rules`；含义：ID 标识。
- `zonesvr.proto` 中的 `ZonePetBoxUnlockReq` 新增字段 2：`int32 unlock_group`；含义：数值字段，通常表示 `unlock_group` 对应的 ID、数量、状态或配置值。
- `zonesvr.proto` 中的 `ZonePhotoAlbumPreviewRsp.PhotoFile` 新增字段 3：`Next.PlayerPhotoAlbumInfo photo_info`；含义：玩家数据结构。
- `zonesvr.proto` 中的 `ZonePhotoAlbumUploadSuccessReq` 新增字段 3：`Next.PlayerPhotoAlbumInfo photo_info`；含义：玩家数据结构。
- `zonesvr.proto` 中的 `ZonePhotoAlbumUploadUrlReq` 新增字段 4：`string photo_md5`；含义：文本或二进制内容，表示 `photo_md5` 对应的数据。
- `zonesvr.proto` 中的 `ZonePlayerShareInfoReq` 新增字段 4：`uint32 activity_id`；含义：活动相关数据。
- `zonesvr.proto` 中的 `ZonePlayerShareInfoRsp` 新增字段 4：`string share_url`；含义：文本或二进制内容，表示 `share_url` 对应的数据。
- `zonesvr.proto` 中的 `ZoneReceivePlayerActivityDisposableRewardRsp` 新增字段 2：`uint32 reward_id`；含义：奖励相关数据。
- `zonesvr_notify.proto` 中的 `ZoneRelationshipReqUnlockNotify` 新增字段 3：`bool reset_unlocked_data`；含义：布尔开关，表示是否满足 `reset_unlocked_data` 对应状态。
- `zonesvr.proto` 中的 `ZoneSceneCancelPlayerTransformReq` 新增字段 2：`int32 transform_avatar`；含义：玩家角色或 Avatar 相关数据。
- `zonesvr.proto` 中的 `ZoneSceneCancelPlayerTransformReq` 新增字段 3：`uint32 eagle_uin`；含义：玩家账号 ID。
- `scene_notify.proto` 中的 `ZoneSceneCommonTipsNotify` 新增字段 3：`repeated int64 param_list`；含义：`param_list` 列表，按字段名可理解为 param / list 相关数据。
- `zonesvr.proto` 中的 `ZoneSceneEndThrowRsp` 新增字段 16：`Next.ThrowStarMagicResult throw_star_magic_result`；含义：根据字段名推断为 `throw_star_magic_result` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `zonesvr.proto` 中的 `ZoneSceneGetFollowInfoRsp` 新增字段 6：`int32 confirm_talk_id`；含义：ID 标识。
- `zonesvr.proto` 中的 `ZoneSceneNpcControlReq` 新增字段 5：`int32 skin_id`；含义：ID 标识。
- `zonesvr_notify.proto` 中的 `ZoneSceneTeleportNotify` 新增字段 25：`bool is_cross_scene`；含义：场景相关数据。
- `zonesvr.proto` 中的 `ZoneSecondaryPasswordCheckRsp` 新增字段 2：`Next.SecondaryPasswordStatus status`；含义：状态。
- `zonesvr.proto` 中的 `ZoneSecondaryPasswordCheckRsp` 新增字段 3：`uint32 status_timestamp`；含义：时间或时间戳。
- `zonesvr.proto` 中的 `ZoneSecondaryPasswordCheckRsp` 新增字段 4：`int32 default_free`；含义：数值字段，通常表示 `default_free` 对应的 ID、数量、状态或配置值。
- `zonesvr.proto` 中的 `ZoneSecondaryPasswordCheckRsp` 新增字段 5：`int32 waiting_duration`；含义：AI 相关数据。
- `zonesvr.proto` 中的 `ZoneSecondaryPasswordForceDisableRsp` 新增字段 3：`Next.SecondaryPasswordStatus status`；含义：状态。
- `zonesvr.proto` 中的 `ZoneSecondaryPasswordForceDisableRsp` 新增字段 4：`uint32 status_timestamp`；含义：时间或时间戳。
- `zonesvr.proto` 中的 `ZoneSecondaryPasswordForceDisableRsp` 新增字段 5：`int32 default_free`；含义：数值字段，通常表示 `default_free` 对应的 ID、数量、状态或配置值。
- `zonesvr.proto` 中的 `ZoneSecondaryPasswordForceDisableRsp` 新增字段 6：`int32 waiting_duration`；含义：AI 相关数据。
- `zonesvr.proto` 中的 `ZoneSetTaskRecoverAllReq` 新增字段 1：`repeated Next.Position bonus_relocate_positions`；含义：位置坐标。

### 删除字段
- `space_data.proto` 中的 `CellData_Normal` 删除字段 22：`Next.CellCompData_EffectDetector comp_data_detector`；含义：根据字段名推断为 `comp_data_detector` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `com_activity.proto` 中的 `PlayerActivityInfo_ActivityPetCollectionData` 删除字段 3：`repeated uint32 collection_pet_rewards`；含义：宠物相关数据。
- `com_action.proto` 中的 `SceneCatchResult` 删除字段 5：`bool is_tech_satisfied`；含义：是否满足技术捕捉、技巧捕捉或特殊捕捉条件。
- `com_action.proto` 中的 `SceneCatchResult` 删除字段 6：`bool is_detected`；含义：布尔开关，表示是否满足 `is_detected` 对应状态。
- `com_action.proto` 中的 `SceneCatchResult` 删除字段 7：`uint32 caught_camp`；含义：数值字段，通常表示 `caught_camp` 对应的 ID、数量、状态或配置值。
- `com_action.proto` 中的 `SceneCatchResult` 删除字段 8：`bool is_visiting`；含义：布尔开关，表示是否满足 `is_visiting` 对应状态。
- `com_action.proto` 中的 `SceneCatchResult` 删除字段 9：`string visit_owner_name`；含义：文本或二进制内容，表示 `visit_owner_name` 对应的数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 4：`uint32 ingame_time`；含义：时间或时间戳。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 5：`uint32 last_update_ingame`；含义：数值字段，通常表示 `last_update_ingame` 对应的 ID、数量、状态或配置值。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 6：`int32 hp_max`；含义：生命值相关数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 7：`uint32 world_lv`；含义：数值字段，通常表示 `world_lv` 对应的 ID、数量、状态或配置值。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 11：`Next.PlayerStoryFlagInfo player_story_flag_info`；含义：玩家数据结构。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 13：`uint32 visit_owner_uin`；含义：玩家账号 ID。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 14：`uint64 visit_owner_obj_id`；含义：ID 标识。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 15：`bool login_leave_visiting`；含义：布尔开关，表示是否满足 `login_leave_visiting` 对应状态。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 16：`uint32 card_label_first_selected`；含义：数值字段，通常表示 `card_label_first_selected` 对应的 ID、数量、状态或配置值。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 17：`uint32 card_label_last_selected`；含义：数值字段，通常表示 `card_label_last_selected` 对应的 ID、数量、状态或配置值。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 18：`uint32 card_skin_selected`；含义：数值字段，通常表示 `card_skin_selected` 对应的 ID、数量、状态或配置值。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 19：`uint32 card_icon_selected`；含义：数值字段，通常表示 `card_icon_selected` 对应的 ID、数量、状态或配置值。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 20：`bytes openid`；含义：账号 openid。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 21：`bytes client_version`；含义：版本号。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 22：`bool is_reconnect`；含义：布尔开关，表示是否满足 `is_reconnect` 对应状态。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 23：`repeated Next.HandbookRecord handbook_records`；含义：图鉴相关数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 24：`uint32 card_music_id`；含义：音乐相关数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 25：`string client_ip`；含义：文本或二进制内容，表示 `client_ip` 对应的数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 26：`string client_ipv6`；含义：文本或二进制内容，表示 `client_ipv6` 对应的数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 27：`repeated int32 fashion_item_wear_data`；含义：道具相关数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 28：`repeated Next.SalonItemWearData salon_item_wear_data`；含义：道具相关数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 29：`int32 quality`；含义：品质或画质相关数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 31：`Next.PlatInfo plat_info`；含义：根据字段名推断为 `plat_info` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 32：`repeated Next.SpecFlowerSeed spec_flower_seeds`；含义：`spec_flower_seeds` 列表，按字段名可理解为 spec / flower / seeds 相关数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 33：`Next.ClientInfo client_info`；含义：根据字段名推断为 `client_info` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 34：`Next.SnsAuthInfo sns_auth_info`；含义：根据字段名推断为 `sns_auth_info` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 35：`repeated int32 fashion_bond_data`；含义：时装相关数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 36：`Next.SceneSeasonInfo season_info`；含义：赛季相关数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 37：`repeated Next.PlayerAppearanceInfo_FashionInfo_WardrobeItem wearing_item`；含义：道具相关数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 38：`Next.PlayerNpcRefreshBanInfo npc_refresh_ban_info`；含义：NPC 相关数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 39：`repeated Next.PlayerFuncBanItem func_ban_items`；含义：道具相关数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 40：`repeated int32 pet_gids`；含义：宠物相关数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 41：`int32 current_select_pet_gid`；含义：宠物相关数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 42：`repeated Next.SceneBasePetData big_world_pet_data`；含义：宠物相关数据。
- `space_data.proto` 中的 `SceneRequiredPlayerInfo` 删除字段 43：`repeated int32 main_team_gids`；含义：AI 相关数据。
- `com_world_map.proto` 中的 `WorldMapEntry_Npc` 删除字段 5：`Next.GlassInfo glass_info`；含义：根据字段名推断为 `glass_info` 相关数据，具体业务含义需要结合客户端逻辑确认。
- `com_world_map.proto` 中的 `WorldMapEntry_Npc` 删除字段 6：`int32 mutation_type`；含义：类型。

## 共有 enum 的枚举值变化

枚举值变化最多的 enum：
- `c2s_cmd.proto` 中的 `ZoneSvrCmd`：264 处；含义：Zone 服务 / 服务器 / Cmd，属于协议消息或数据结构，通常表示相关结构或枚举。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr`：32 处；含义：MOBA / RET / Zone 服务 / 错误码，属于协议消息或数据结构，通常表示错误码枚举。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr`：28 处；含义：MOBA / RET / 场景 / 错误码，属于协议消息或数据结构，通常表示错误码枚举。
- `xls_enum.proto` 中的 `SuitAiEffect`：24 处；含义：Suit / AI / 效果，属于协议消息或数据结构，通常表示相关结构或枚举。
- `xls_enum.proto` 中的 `RPBehaviorType`：22 处；含义：RP / Behavior / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `ActionType`：21 处；含义：动作 / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `com_gm.proto` 中的 `SceneGmType`：17 处；含义：场景 / Gm / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `FunctionEntrance`：16 处；含义：Function / Entrance，属于协议消息或数据结构，通常表示相关结构或枚举。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd`：15 处；含义：Zone 服务 / 服务器 / Gm / Cmd，属于协议消息或数据结构，通常表示相关结构或枚举。
- `xls_enum.proto` 中的 `RedPointReason`：14 处；含义：Red / Point / 原因，属于协议消息或数据结构，通常表示相关结构或枚举。
- `space_action.proto` 中的 `SpaceActionType.ENUM`：13 处；含义：Space / 动作 / 类型 / ENUM，属于协议消息或数据结构，通常表示相关结构或枚举。
- `com_account.proto` 中的 `FlowReason`：13 处；含义：Flow / 原因，属于协议消息或数据结构，通常表示相关结构或枚举。
- `xls_enum.proto` 中的 `PlayerStoryFlagEnum`：12 处；含义：玩家 / Story / Flag / 枚举，属于协议消息或数据结构，通常表示相关结构或枚举。
- `xls_enum.proto` 中的 `SpaceActorLogicStatus`：10 处；含义：Space / 场景对象 / Logic / 状态，属于协议消息或数据结构，通常表示状态枚举或状态结构。
- `xls_enum.proto` 中的 `BuffType`：9 处；含义：Buff / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `BagCharmPrivilegeEffect`：9 处；含义：Bag / Charm / Privilege / 效果，属于协议消息或数据结构，通常表示相关结构或枚举。
- `xls_enum.proto` 中的 `ActivityType`：9 处；含义：活动 / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `RefreshRuleConf`：8 处；含义：刷新 / Rule / Conf，属于协议消息或数据结构，通常表示相关结构或枚举。
- `xls_enum.proto` 中的 `SceneRideAllActiveType`：5 处；含义：场景 / Ride / All / Active / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `PlayerConditionType`：5 处；含义：玩家 / 条件 / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `ActiviyMixSlotFunciton`：5 处；含义：Activiy / 混合 / Slot / Funciton，属于协议消息或数据结构，通常表示相关结构或枚举。
- `com_friend_data.proto` 中的 `FriendSource`：5 处；含义：好友 / 来源，属于协议消息或数据结构，通常表示来源枚举。
- `xls_enum.proto` 中的 `MapIconShowType`：4 处；含义：地图 / 图标 / Show / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `com_pet.proto` 中的 `PetDataBitFlag`：4 处；含义：宠物 / 数据 / Bit / Flag，属于协议消息或数据结构，通常表示相关结构或枚举。
- `battle_data.proto` 中的 `PetSkillRoundData.FLAG`：4 处；含义：宠物 / Skill / Round / 数据 / FLAG，属于协议消息或数据结构，通常表示相关结构或枚举。
- `xls_enum.proto` 中的 `VisualItem`：3 处；含义：Visual / Item，属于协议消息或数据结构，通常表示相关结构或枚举。
- `xls_enum.proto` 中的 `TaskKeyType`：3 处；含义：Task / Key / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `PlayerFunctionBanType`：3 处；含义：玩家 / Function / 禁用 / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `EffectType`：3 处；含义：效果 / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `CloseExpActionType`：3 处；含义：Close / 经验 / 动作 / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `com_action.proto` 中的 `PlayerTransformCancelReason`：3 处；含义：玩家 / Transform / 取消 / 原因，属于协议消息或数据结构，通常表示相关结构或枚举。
- `xls_enum.proto` 中的 `ShareButtonType`：2 处；含义：Share / Button / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `SceneEventType`：2 处；含义：场景 / 事件 / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `SceneAbilityDisableCode`：2 处；含义：场景 / Ability / 禁用 / Code，属于协议消息或数据结构，通常表示相关结构或枚举。
- `xls_enum.proto` 中的 `RewardTag`：2 处；含义：奖励 / 标签，属于协议消息或数据结构，通常表示标签枚举。
- `xls_enum.proto` 中的 `NpcSceneCommandType`：2 处；含义：NPC / 场景 / Command / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `MonsterDifficultyType`：2 处；含义：Monster / Difficulty / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `ItemBehavior`：2 处；含义：Item / Behavior，属于协议消息或数据结构，通常表示相关结构或枚举。
- `xls_enum.proto` 中的 `FurniturelnteractType`：2 处；含义：Furniturelnteract / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `FilterRule`：2 处；含义：筛选 / Rule，属于协议消息或数据结构，通常表示相关结构或枚举。
- `xls_enum.proto` 中的 `BuffGroupSign`：2 处；含义：Buff / Group / 签到，属于协议消息或数据结构，通常表示相关结构或枚举。
- `xls_enum.proto` 中的 `BattleType`：2 处；含义：战斗 / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `BattleAIStatus`：2 处；含义：战斗 / AI / 状态，属于协议消息或数据结构，通常表示状态枚举或状态结构。
- `xls_enum.proto` 中的 `AutoIncrementType`：2 处；含义：自动 / Increment / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `AttributeType`：2 处；含义：Attribute / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `AreaType`：2 处；含义：Area / 类型，属于协议消息或数据结构，通常表示类型枚举。
- `xls_enum.proto` 中的 `ActivityMonitorEvent`：2 处；含义：活动 / Monitor / 事件，属于协议消息或数据结构，通常表示相关结构或枚举。
- `space_action.proto` 中的 `SpaceAct_SetNpcPosReason`：2 处；含义：Space / Act / 设置 / NPC / Pos / 原因，属于协议消息或数据结构，通常表示相关结构或枚举。
- `errorcode.proto` 中的 `MOBA_RET.HttpsvrErr`：2 处；含义：MOBA / RET / Httpsvr / 错误码，属于协议消息或数据结构，通常表示错误码枚举。
- `errorcode.proto` 中的 `MOBA_RET.ErrorCode`：2 处；含义：MOBA / RET / 错误 / Code，属于协议消息或数据结构，通常表示相关结构或枚举。

### 同一数值改名
- `xls_enum.proto` 中的 `ActivityType` 数值 45：`ATP_BOSS_CHALLENGE` -> `ATP_LEGENDARY_CHALLENGE`；含义：旧值 Boss 挑战活动类型。 新值 传说挑战活动类型。
- `xls_enum.proto` 中的 `ActivityType` 数值 47：`ATP_COMMEN_OPTION` -> `ATP_SIGN_REWARD`；含义：旧值 通用选项活动类型，旧名称疑似拼写不规范。 新值 签到奖励活动类型。
- `xls_enum.proto` 中的 `EffectType` 数值 87：`ET_COMPETITION` -> `ET_CROSS_TRANSFER`；含义：旧值 竞赛效果类型。 新值 跨区域或跨服转移效果类型。
- `xls_enum.proto` 中的 `EffectType` 数值 88：`ET_TRIGGER` -> `ET_COPY`；含义：旧值 触发器效果类型。 新值 复制效果类型。
- `xls_enum.proto` 中的 `GuideActionType` 数值 6：`GAT_SCROLL_RIGT` -> `GAT_SCROLL_RIGHT`；含义：旧值 引导滚动到右侧动作，旧名称拼写错误。 新值 引导滚动到右侧动作。
- `xls_enum.proto` 中的 `PlayerFunctionBanType` 数值 123：`PFBT_END` -> `PFBT_RIDE_OFF`；含义：旧值 旧的功能封禁枚举结束标记。 新值 禁止或关闭骑乘功能。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 数值 6388：`ZONE_ACTIVITY_SELECT_TRACK_CONTENTS_REQ` -> `ZONE_ACTIVITY_PHOTO_CONTEST_EVALUATION_NOTIFY`；含义：旧值 活动 / 选择 / 跟踪 / 内容 / 请求，属于 Zone 服务命令号，请求命令。 新值 活动 / 照片 / 比赛 / 评审 / 通知，属于 Zone 服务命令号，通知命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 数值 6389：`ZONE_ACTIVITY_SELECT_TRACK_CONTENTS_RSP` -> `ZONE_ACTIVITY_PHOTO_CONTEST_LIKE_NOTIFY`；含义：旧值 活动 / 选择 / 跟踪 / 内容 / 响应，属于 Zone 服务命令号，响应命令。 新值 活动 / 照片 / 比赛 / 点赞 / 通知，属于 Zone 服务命令号，通知命令。

### 新增枚举值
- `xls_enum.proto` 中的 `ActionType` 新增数值 89：`ACT_PETHATCH`；含义：宠物孵化动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 152：`ACT_RECALL_GIFT_PACKAGE`；含义：回流活动礼包动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 153：`ACT_RECALL_PETGIFT`；含义：回流宠物礼物动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 154：`ACT_RECALL_ACTIVITY_OPEN`；含义：打开回流活动动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 207：`ACT_KNOCK_SCAREDBOX`；含义：敲击惊吓盒或惊吓箱动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 208：`ACT_BLINDBOX_IN`；含义：进入盲盒玩法或盲盒状态动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 209：`ACT_BLINDBOX_OUT`；含义：离开盲盒玩法或盲盒状态动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 210：`ACT_BATTLE_WATCH_LITE`；含义：轻量版战斗观看或观战动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 211：`ACT_CANNON_FIRE`；含义：炮台开火动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 212：`ACT_SIT_WORLD`；含义：大世界坐下动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 213：`ACT_TEMP_RIDING`；含义：临时骑乘动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 214：`ACT_TELEPORT_SE`；含义：传送特效或传送音效动作，`SE` 可能表示 sound effect 或 special effect。
- `xls_enum.proto` 中的 `ActionType` 新增数值 372：`ACT_DRAW_A_LOTTERY`；含义：抽奖动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 400：`ACT_FURNITURE_PLAY_ANIMATION`；含义：家具播放动画动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 401：`ACT_FURNITURE_CHANGE_BGM`；含义：家具切换背景音乐动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 402：`ACT_VIEW_WALL_ART`；含义：查看墙上装饰画或墙面艺术品动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 10006：`ACT_BOX_BATTLE`；含义：盒子战斗动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 10161：`ACT_CHANGE_CONTENT_SIZE`；含义：改变内容尺寸动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 10162：`ACT_CHANGE_CONTENT_SIZE_EFFECT`；含义：改变内容尺寸的效果动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 10163：`ACT_GRASS_TRIAL_NODE`；含义：草系试炼节点动作。
- `xls_enum.proto` 中的 `ActionType` 新增数值 10164：`ACT_AUTO_OPENBOX`；含义：自动开箱动作。
- `xls_enum.proto` 中的 `ActivityMixSlot` 新增数值 6：`AMSLOT_6`；含义：活动混合槽位 6。
- `xls_enum.proto` 中的 `ActivityMonitorEvent` 新增数值 24：`AME_PLAYER_TRANSFORM_ONLINE_TIME`；含义：玩家变身玩法在线时长监控事件。
- `xls_enum.proto` 中的 `ActivityMonitorEvent` 新增数值 25：`AME_PLAYER_TRANSFORM_EAGLE_CAPTURE`；含义：玩家变身为鹰或鹰形态捕获相关监控事件。
- `xls_enum.proto` 中的 `ActivityType` 新增数值 46：`ATP_TAKEPHOTO_COMPETITION`；含义：拍照比赛或摄影比赛活动类型。
- `xls_enum.proto` 中的 `ActivityType` 新增数值 48：`ATP_PET_TRIP`；含义：宠物旅行活动类型。
- `xls_enum.proto` 中的 `ActivityType` 新增数值 49：`ATP_GLOBAL_CHALLENGE`；含义：GLOBAL / 挑战，属于 活动类型。
- `xls_enum.proto` 中的 `ActivityType` 新增数值 50：`ATP_ACTIVITY_RECALL_STARLIGHT`；含义：活动 / 回流 / STARLIGHT，属于 活动类型。
- `xls_enum.proto` 中的 `ActivityType` 新增数值 51：`ATP_ACTIVITY_RECALL_BP`；含义：活动 / 回流 / BP，属于 活动类型。
- `xls_enum.proto` 中的 `ActivityType` 新增数值 52：`ATP_ACTIVITY_RECALL`；含义：活动 / 回流，属于 活动类型。
- `xls_enum.proto` 中的 `ActivityType` 新增数值 53：`ATP_PRE_DOWNLOAD`；含义：预 / 下载，属于 活动类型。
- `xls_enum.proto` 中的 `ActiviyMixSlotFunciton` 新增数值 3：`AMSF_TASK`；含义：AMSF / 任务，属于 ActiviyMixSlotFunciton。
- `xls_enum.proto` 中的 `ActiviyMixSlotFunciton` 新增数值 4：`AMSF_CHECK_BAGITEM`；含义：AMSF / 检查 / BAGITEM，属于 ActiviyMixSlotFunciton。
- `xls_enum.proto` 中的 `ActiviyMixSlotFunciton` 新增数值 5：`AMSF_SHOW_BAGITEM`；含义：AMSF / 展示 / BAGITEM，属于 ActiviyMixSlotFunciton。
- `xls_enum.proto` 中的 `ActiviyMixSlotFunciton` 新增数值 6：`AMSF_PET_INFORMATION`；含义：AMSF / 宠物 / INFORMATION，属于 ActiviyMixSlotFunciton。
- `xls_enum.proto` 中的 `ActiviyMixSlotFunciton` 新增数值 7：`AMSF_TASK_REAWAD`；含义：AMSF / 任务 / REAWAD，属于 ActiviyMixSlotFunciton。
- `space_data.proto` 中的 `ActorInfo_HomeBasicInfo.ReloadReason` 新增数值 5：`RELOAD_REASON_PLACE_PET_CHANGED`；含义：RELOAD / REASON / PLACE / 宠物 / CHANGED，属于 ActorInfo_HomeBasicInfo.ReloadReason。
- `xls_enum.proto` 中的 `AdventureRecord` 新增数值 5：`AR_COLLECTED_MUTATION_PET_NUM`；含义：AR / COLLECTED / MUTATION / 宠物 / NUM，属于 AdventureRecord。
- `xls_enum.proto` 中的 `AreaType` 新增数值 3：`AREAT_CIRCLE`；含义：AREAT / CIRCLE，属于 AreaType。
- `xls_enum.proto` 中的 `AreaType` 新增数值 4：`AREAT_RECTANGLE`；含义：AREAT / RECTANGLE，属于 AreaType。
- `xls_enum.proto` 中的 `AttributeType` 新增数值 95：`AI_BOX_SHIELD`；含义：AI / 盒子 / SHIELD，属于 AttributeType。
- `xls_enum.proto` 中的 `AttributeType` 新增数值 96：`AI_BOX_SHIELD_MAX`；含义：AI / 盒子 / SHIELD / MAX，属于 AttributeType。
- `xls_enum.proto` 中的 `AutoIncrementType` 新增数值 9：`AIIT_HAPPY_VALUE`；含义：AIIT / HAPPY / VALUE，属于 AutoIncrementType。
- `xls_enum.proto` 中的 `AutoIncrementType` 新增数值 10：`AIIT_WISH_CHOICE`；含义：AIIT / 心愿 / 选择，属于 AutoIncrementType。
- `xls_enum.proto` 中的 `BagCharmPrivilegeEffect` 新增数值 10：`BGCPE_XIAOLINGGU`；含义：BGCPE / XIAOLINGGU，属于 BagCharmPrivilegeEffect。
- `xls_enum.proto` 中的 `BagCharmPrivilegeEffect` 新增数值 11：`BGCPE_KUKUGU`；含义：BGCPE / KUKUGU，属于 BagCharmPrivilegeEffect。
- `xls_enum.proto` 中的 `BagCharmPrivilegeEffect` 新增数值 12：`BGCPE_BENBOSHU`；含义：BGCPE / BENBOSHU，属于 BagCharmPrivilegeEffect。
- `xls_enum.proto` 中的 `BagCharmPrivilegeEffect` 新增数值 13：`BGCPE_HAIBAOZHANSHI`；含义：BGCPE / HAIBAOZHANSHI，属于 BagCharmPrivilegeEffect。
- `xls_enum.proto` 中的 `BagCharmPrivilegeEffect` 新增数值 14：`BGCPE_HAIKUICHONG`；含义：BGCPE / HAIKUICHONG，属于 BagCharmPrivilegeEffect。
- `xls_enum.proto` 中的 `BagCharmPrivilegeEffect` 新增数值 15：`BGCPE_XIAOXIANGGUAI`；含义：BGCPE / XIAOXIANGGUAI，属于 BagCharmPrivilegeEffect。
- `xls_enum.proto` 中的 `BagCharmPrivilegeEffect` 新增数值 16：`BGCPE_XIAOYE`；含义：BGCPE / XIAOYE，属于 BagCharmPrivilegeEffect。
- `xls_enum.proto` 中的 `BagCharmPrivilegeEffect` 新增数值 17：`BGCPE_WUDA`；含义：BGCPE / WUDA，属于 BagCharmPrivilegeEffect。
- `xls_enum.proto` 中的 `BagCharmPrivilegeEffect` 新增数值 18：`BGCPE_QIULUO`；含义：BGCPE / QIULUO，属于 BagCharmPrivilegeEffect。
- `xls_enum.proto` 中的 `BagItemType` 新增数值 24：`BI_CAMERA_SKIN`；含义：BI / CAMERA / SKIN，属于 BagItemType。
- `xls_enum.proto` 中的 `BattleAIStatus` 新增数值 29：`BAS_BOX`；含义：BAS / 盒子，属于 BattleAIStatus。
- `xls_enum.proto` 中的 `BattleAIStatus` 新增数值 30：`BAS_BACK_OF_HEAD_TALENT`；含义：BAS / BACK / OF / HEAD / TALENT，属于 BattleAIStatus。
- `xls_enum.proto` 中的 `BattleEvent` 新增数值 72：`BEVT_AFTER_EVOLUTE`；含义：BEVT / AFTER / EVOLUTE，属于 BattleEvent。
- `battle_data.proto` 中的 `BattlePerformType` 新增数值 51：`BPT_BOX_SHIELD_BREAK`；含义：BPT / 盒子 / SHIELD / BREAK，属于 BattlePerformType。
- `battle_data.proto` 中的 `BattlePerformType` 新增数值 52：`BPT_VC_FINISH_PERFORM`；含义：BPT / VC / 完成 / PERFORM，属于 BattlePerformType。
- `xls_enum.proto` 中的 `BattleType` 新增数值 35：`BT_PVP_SCARE`；含义：BT / PVP / SCARE，属于 BattleType。
- `xls_enum.proto` 中的 `BattleType` 新增数值 36：`BT_TEST_PVP_AUTO_SKILL_PERFORMANCE`；含义：BT / TEST / PVP / 自动 / 技能 / PERFORMANCE，属于 BattleType。
- `xls_enum.proto` 中的 `BelongSystem` 新增数值 4：`BS_RECALL_ACTIVITY`；含义：BS / 回流 / 活动，属于 BelongSystem。
- `xls_enum.proto` 中的 `BonusPetFieldMatchType` 新增数值 5：`FIELD_MATCH_FIRST`；含义：FIELD / 匹配 / FIRST，属于 BonusPetFieldMatchType。
- `xls_enum.proto` 中的 `BonusVariableType` 新增数值 7：`BVT_ACCU_NUM`；含义：BVT / ACCU / NUM，属于 BonusVariableType。
- `xls_enum.proto` 中的 `BuffGroupSign` 新增数值 30：`BGS_FANTASTIC_BOX`；含义：BGS / FANTASTIC / 盒子，属于 BuffGroupSign。
- `xls_enum.proto` 中的 `BuffGroupSign` 新增数值 31：`BGS_STATS`；含义：BGS / STATS，属于 BuffGroupSign。
- `xls_enum.proto` 中的 `BuffType` 新增数值 144：`BFT_O_FORTYFOUR`；含义：BFT / O / FORTYFOUR，属于 BuffType。
- `xls_enum.proto` 中的 `BuffType` 新增数值 145：`BFT_O_FORTYFIVE`；含义：BFT / O / FORTYFIVE，属于 BuffType。
- `xls_enum.proto` 中的 `BuffType` 新增数值 146：`BFT_O_FORTYSIX`；含义：BFT / O / FORTYSIX，属于 BuffType。
- `xls_enum.proto` 中的 `BuffType` 新增数值 147：`BFT_O_FORTYSEVEN`；含义：BFT / O / FORTYSEVEN，属于 BuffType。
- `xls_enum.proto` 中的 `BuffType` 新增数值 148：`BFT_O_FORTYEIGHT`；含义：BFT / O / FORTYEIGHT，属于 BuffType。
- `xls_enum.proto` 中的 `BuffType` 新增数值 151：`BFT_O_FIFTYONE`；含义：BFT / O / FIFTYONE，属于 BuffType。
- `xls_enum.proto` 中的 `BuffType` 新增数值 153：`BFT_O_FIFTYTHREE`；含义：BFT / O / FIFTYTHREE，属于 BuffType。
- `xls_enum.proto` 中的 `BuffType` 新增数值 154：`BFT_O_FIFTYFOUR`；含义：BFT / O / FIFTYFOUR，属于 BuffType。
- `xls_enum.proto` 中的 `BuffType` 新增数值 155：`BFT_O_FIFTYFIVE`；含义：BFT / O / FIFTYFIVE，属于 BuffType。
- `space_data.proto` 中的 `ClientOperationType` 新增数值 8：`COP_TAKE_PHOTO_EMOJI_POSE`；含义：COP / TAKE / 照片 / EMOJI / POSE，属于 ClientOperationType。
- `xls_enum.proto` 中的 `CloseExpActionType` 新增数值 14：`CEA_LLM_ACTION`；含义：CEA / LLM / 行为，属于 CloseExpActionType。
- `xls_enum.proto` 中的 `CloseExpActionType` 新增数值 15：`CEA_LLM_EMOJI`；含义：CEA / LLM / EMOJI，属于 CloseExpActionType。
- `xls_enum.proto` 中的 `CloseExpActionType` 新增数值 16：`CEA_LLM_TEXT`；含义：CEA / LLM / TEXT，属于 CloseExpActionType。
- `scene_notify.proto` 中的 `CommonTipsSource` 新增数值 3：`CTS_PET_REPORT_LIMIT`；含义：CTS / 宠物 / 上报 / LIMIT，属于 CommonTipsSource。
- `com_actor.proto` 中的 `ControllableNpcOpType` 新增数值 5：`CNOT_UNLOCK_SKIN`；含义：CNOT / 解锁 / SKIN，属于 ControllableNpcOpType。
- `com_actor.proto` 中的 `ControllableNpcOpType` 新增数值 6：`CNOT_SET_SKIN`；含义：CNOT / 设置 / SKIN，属于 ControllableNpcOpType。
- `xls_enum.proto` 中的 `EffectType` 新增数值 90：`ET_INSERT_SKILL`；含义：INSERT / 技能，属于 效果类型。
- `xls_enum.proto` 中的 `FashionRingsTag` 新增数值 0：`FRT_NONETAG`；含义：FRT / NONETAG，属于 FashionRingsTag。
- `xls_enum.proto` 中的 `FashionTopsTag` 新增数值 0：`FTT_NONETAG`；含义：FTT / NONETAG，属于 FashionTopsTag。
- `xls_enum.proto` 中的 `FilterRule` 新增数值 14：`FIL_SEASON`；含义：FIL / SEASON，属于 FilterRule。
- `xls_enum.proto` 中的 `FilterRule` 新增数值 15：`FIL_ROLLBACK_TYPE`；含义：FIL / ROLLBACK / TYPE，属于 FilterRule。
- `com_account.proto` 中的 `FlowModule` 新增数值 32：`FLOW_MODULE_NPC_LOTTERY`；含义：FLOW / MODULE / NPC / 抽奖，属于 FlowModule。
- `com_account.proto` 中的 `FlowModule` 新增数值 33：`FLOW_MODULE_CARD`；含义：FLOW / MODULE / 卡牌，属于 FlowModule。
- `com_account.proto` 中的 `FlowReason` 新增数值 236：`FLOW_REASON_ACTIVITY_PET_TRIP`；含义：FLOW / REASON / 活动 / 宠物 / 旅行，属于 FlowReason。
- `com_account.proto` 中的 `FlowReason` 新增数值 237：`FLOW_REASON_ACTIVITY_PET_TRIP_LOTTERY_REWARD`；含义：FLOW / REASON / 活动 / 宠物 / 旅行 / 抽奖 / 奖励，属于 FlowReason。
- `com_account.proto` 中的 `FlowReason` 新增数值 238：`FLOW_REASON_PET_BACKTRACK`；含义：FLOW / REASON / 宠物 / BACKTRACK，属于 FlowReason。
- `com_account.proto` 中的 `FlowReason` 新增数值 240：`FLOW_REASON_ACTIVITY_RECALL`；含义：FLOW / REASON / 活动 / 回流，属于 FlowReason。
- `com_account.proto` 中的 `FlowReason` 新增数值 241：`FLOW_REASON_ACTIVITY_INVITE_REGISTER`；含义：FLOW / REASON / 活动 / INVITE / REGISTER，属于 FlowReason。
- `com_account.proto` 中的 `FlowReason` 新增数值 242：`FLOW_REASON_ACTIVITY_PHOTO_CONTEST`；含义：FLOW / REASON / 活动 / 照片 / 比赛，属于 FlowReason。
- `com_account.proto` 中的 `FlowReason` 新增数值 243：`FLOW_REASON_ACTIVITY_GLOBAL_CHALLENGE`；含义：FLOW / REASON / 活动 / GLOBAL / 挑战，属于 FlowReason。
- `com_account.proto` 中的 `FlowReason` 新增数值 244：`FLOW_REASON_NPC_LOTTERY`；含义：FLOW / REASON / NPC / 抽奖，属于 FlowReason。
- `com_account.proto` 中的 `FlowReason` 新增数值 248：`FLOW_REASON_ACTIVITY_BASE_MIX`；含义：FLOW / REASON / 活动 / 基础 / MIX，属于 FlowReason。
- `com_account.proto` 中的 `FlowReason` 新增数值 249：`FLOW_REASON_ACTIVITY_SIGN_REWARD`；含义：FLOW / REASON / 活动 / SIGN / 奖励，属于 FlowReason。
- `com_account.proto` 中的 `FlowReason` 新增数值 250：`FLOW_REASON_ACTIVITY_PRE_DOWNLOAD`；含义：FLOW / REASON / 活动 / 预 / 下载，属于 FlowReason。
- `com_account.proto` 中的 `FlowReason` 新增数值 251：`FLOW_REASON_PET_BACKTRACK_BY_PET_RELEASE`；含义：FLOW / REASON / 宠物 / BACKTRACK / BY / 宠物 / RELEASE，属于 FlowReason。
- `com_account.proto` 中的 `FlowReason` 新增数值 257：`FLOW_REASON_EXCHANGE_WISHINGSTAR`；含义：FLOW / REASON / EXCHANGE / WISHINGSTAR，属于 FlowReason。
- `com_friend_data.proto` 中的 `FriendSource` 新增数值 4：`FS_PVP_COMBAT`；含义：FS / PVP / COMBAT，属于 FriendSource。
- `com_friend_data.proto` 中的 `FriendSource` 新增数值 5：`FS_TOGETHER`；含义：FS / TOGETHER，属于 FriendSource。
- `com_friend_data.proto` 中的 `FriendSource` 新增数值 6：`FS_TEAM_COMBAT`；含义：FS / 队伍 / COMBAT，属于 FriendSource。
- `com_friend_data.proto` 中的 `FriendSource` 新增数值 7：`FS_TOY_INTERACTION`；含义：FS / TOY / INTERACTION，属于 FriendSource。
- `com_friend_data.proto` 中的 `FriendSource` 新增数值 8：`FS_VISIT_HOME`；含义：FS / 访问 / 家园，属于 FriendSource。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 81：`FE_AI_COACH`；含义：FE / AI / 教练，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 82：`FE_TAPTAP_RATING`；含义：FE / TAPTAP / RATING，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 83：`FE_PRE_DOWNLOAD`；含义：FE / 预 / 下载，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 84：`FE_RP_DRESSUP`；含义：FE / RP / DRESSUP，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 85：`FE_IOS_RATING`；含义：FE / IOS / RATING，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 86：`FE_S1_HANDBOOK`；含义：FE / S1 / 图鉴，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 87：`FE_S2_HANDBOOK`；含义：FE / S2 / 图鉴，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 88：`FE_PHOTO_CONTEST`；含义：FE / 照片 / 比赛，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 89：`FE_RANKBOARD`；含义：FE / RANKBOARD，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 81010000：`FE_AI_COACH_PREPARE`；含义：FE / AI / 教练 / PREPARE，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 81020000：`FE_AI_COACH_BATTLE`；含义：FE / AI / 教练 / 战斗，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 81030000：`FE_AI_COACH_FRIEND`；含义：FE / AI / 教练 / 好友，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 81040000：`FE_AI_COACH_CHAT`；含义：FE / AI / 教练 / CHAT，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 81050000：`FE_AI_COACH_ACTIVITY`；含义：FE / AI / 教练 / 活动，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 81060000：`FE_AI_COACH_TEAM`；含义：FE / AI / 教练 / 队伍，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FunctionEntrance` 新增数值 89010000：`FE_RANKBOARD_FETCH_DB`；含义：FE / RANKBOARD / FETCH / DB，属于 FunctionEntrance。
- `xls_enum.proto` 中的 `FurniturelnteractType` 新增数值 4：`FIT_PLAY_ANIMATION`；含义：FIT / 播放 / 动画，属于 FurniturelnteractType。
- `xls_enum.proto` 中的 `FurniturelnteractType` 新增数值 5：`FIT_PCT_UI`；含义：FIT / PCT / UI，属于 FurniturelnteractType。
- `xls_enum.proto` 中的 `HABITAT_FLAG` 新增数值 4：`HAB_FLY_WATER`；含义：HAB / FLY / WATER，属于 HABITAT_FLAG。
- `xls_enum.proto` 中的 `HideTagType` 新增数值 4：`HD_SPEC_TASK`；含义：HD / SPEC / 任务，属于 HideTagType。
- `xls_enum.proto` 中的 `InteractConditionType` 新增数值 2：`INTERACT_COND_NPC_CREATOR_AND_TOGETHER`；含义：INTERACT / COND / NPC / CREATOR / AND / TOGETHER，属于 InteractConditionType。
- `xls_enum.proto` 中的 `InterfaceType` 新增数值 20：`IT_PET_TRIP`；含义：IT / 宠物 / 旅行，属于 InterfaceType。
- `xls_enum.proto` 中的 `ItemBehavior` 新增数值 46：`IB_PET_HATCH_PROCESS_ADD`；含义：IB / 宠物 / HATCH / PROCESS / 添加，属于 ItemBehavior。
- `xls_enum.proto` 中的 `ItemBehavior` 新增数值 48：`IB_UNLOCK_CAMERA_SKIN`；含义：IB / 解锁 / CAMERA / SKIN，属于 ItemBehavior。
- `errorcode.proto` 中的 `MOBA_RET.ErrorCode` 新增数值 1138：`ERR_COMMON_ADD_COIN_OFLOWLOW`；含义：ERR / COMMON / 添加 / COIN / OFLOWLOW，属于 MOBA_RET.ErrorCode。
- `errorcode.proto` 中的 `MOBA_RET.ErrorCode` 新增数值 1139：`ERR_COMMON_GM_RPC_HAS_BEEN_BANNED`；含义：ERR / COMMON / GM / RPC / HAS / BEEN / BANNED，属于 MOBA_RET.ErrorCode。
- `errorcode.proto` 中的 `MOBA_RET.FriendError` 新增数值 13027：`ERR_FRIEND_GET_PLAT_FRIEND_NO_AUTH`；含义：ERR / 好友 / 获取 / PLAT / 好友 / NO / AUTH，属于 MOBA_RET.FriendError。
- `errorcode.proto` 中的 `MOBA_RET.HttpsvrErr` 新增数值 18362：`ERR_HTTPSVR_PHOTO_ALBUM_PHOTO_CONTEST_TSS_CHECK_FAIL`；含义：ERR / HTTPSVR / 照片 / ALBUM / 照片 / 比赛 / 安全检查 / 检查 / FAIL，属于 MOBA_RET.HttpsvrErr。
- `errorcode.proto` 中的 `MOBA_RET.HttpsvrErr` 新增数值 18363：`ERR_HTTPSVR_PHOTO_ALBUM_PHOTO_CONTEST_TSS_CHECK_TIMEOUT`；含义：ERR / HTTPSVR / 照片 / ALBUM / 照片 / 比赛 / 安全检查 / 检查 / TIMEOUT，属于 MOBA_RET.HttpsvrErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 50326：`ERR_SCENE_HOME_PET_GATHER_EGG_PKG_FULL`；含义：ERR / 场景 / 家园 / 宠物 / GATHER / EGG / PKG / FULL，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 50607：`ERR_SCENE_BONUS_LIMIT_REACHED`；含义：ERR / 场景 / BONUS / LIMIT / REACHED，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 50766：`ERR_SCENE_BOX_BATTLE_ID_NOT_FOUND`；含义：ERR / 场景 / 盒子 / 战斗 / ID / NOT / FOUND，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 50767：`ERR_SCENE_BOX_TYPE_INVALID`；含义：ERR / 场景 / 盒子 / TYPE / INVALID，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 50768：`ERR_SCENE_RELATION_INTERACT_TOO_FAR_AWAY`；含义：ERR / 场景 / RELATION / INTERACT / TOO / FAR / AWAY，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 50769：`ERR_SCENE_CAMERA_SKIN_LOCKED`；含义：ERR / 场景 / CAMERA / SKIN / LOCKED，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 50814：`ERR_SCENE_THROW_CATCH_FAIL_TARGET_NOT_IN_AOI`；含义：ERR / 场景 / 投掷 / CATCH / FAIL / TARGET / NOT / IN / AOI，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 50815：`ERR_SCENE_OPTION_CFG_INTERACT_CONDITION_NOT_ALLOW`；含义：ERR / 场景 / OPTION / CFG / INTERACT / CONDITION / NOT / ALLOW，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51101：`ERR_SCENE_AVATAR_LEAVE_ROLEPLAY_FAIL_DATA_INCONSISTENT`；含义：ERR / 场景 / 角色 / LEAVE / ROLEPLAY / FAIL / 数据 / INCONSISTENT，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51102：`ERR_SCENE_NPC_PROP_CFG_NOT_FOUND`；含义：ERR / 场景 / NPC / PROP / CFG / NOT / FOUND，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51103：`ERR_SCENE_OPTION_BLACK_OR_WHITE_LIST_UIN_NOT_FOUND`；含义：ERR / 场景 / OPTION / BLACK / OR / WHITE / 列表 / UIN / NOT / FOUND，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51104：`ERR_SCENE_OPTION_BLACK_OR_WHITE_LIST_UIN_ALREADY_EXIST`；含义：ERR / 场景 / OPTION / BLACK / OR / WHITE / 列表 / UIN / ALREADY / EXIST，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51105：`ERR_SCENE_OPTION_INTERACT_FAIL_ROLE_NOT_IN_WHITELIST_UINS`；含义：ERR / 场景 / OPTION / INTERACT / FAIL / 角色 / NOT / IN / WHITELIST / UINS，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51106：`ERR_SCENE_OPTION_INTERACT_FAIL_ROLE_IN_BLACKLIST_UINS`；含义：ERR / 场景 / OPTION / INTERACT / FAIL / 角色 / IN / BLACKLIST / UINS，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51107：`ERR_SCENE_OPTION_INTERACT_BLIND_BATTLE_FAIL_NO_AVATAR_IN_BOX`；含义：ERR / 场景 / OPTION / INTERACT / BLIND / 战斗 / FAIL / NO / 角色 / IN / 盒子，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51108：`ERR_SCENE_NPC_PROP_NOT_FOUND`；含义：ERR / 场景 / NPC / PROP / NOT / FOUND，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51200：`ERR_SCENE_THROW_CATCH_FINISH_FAIL_CANNOT_FOUDN_THROWID`；含义：ERR / 场景 / 投掷 / CATCH / 完成 / FAIL / CANNOT / FOUDN / THROWID，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51201：`ERR_SCENE_THROW_CATCH_BEGIN_FAIL_REPEATED_THROWID`；含义：ERR / 场景 / 投掷 / CATCH / 开始 / FAIL / REPEATED / THROWID，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51301：`ERR_SCENE_ABNORMAL_STATUS_IN_CD`；含义：ERR / 场景 / ABNORMAL / 状态 / IN / CD，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51302：`ERR_SCENE_ABNORMAL_STATUS_PRIORITY_NOT_MEET`；含义：ERR / 场景 / ABNORMAL / 状态 / PRIORITY / NOT / MEET，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51303：`ERR_SCENE_ABNORMAL_STATUS_NOT_ALLOWED`；含义：ERR / 场景 / ABNORMAL / 状态 / NOT / ALLOWED，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51304：`ERR_SCENE_ABNORMAL_STATUS_ALREADY_EXIST`；含义：ERR / 场景 / ABNORMAL / 状态 / ALREADY / EXIST，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51305：`ERR_SCENE_ABNORMAL_STATUS_SOURCE_NOT_WHITELIST`；含义：ERR / 场景 / ABNORMAL / 状态 / SOURCE / NOT / WHITELIST，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51306：`ERR_SCENE_BATTLE_NPC_INVALID`；含义：ERR / 场景 / 战斗 / NPC / INVALID，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51307：`ERR_SCENE_BATTLE_NPC_NOT_FOUND`；含义：ERR / 场景 / 战斗 / NPC / NOT / FOUND，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51308：`ERR_SCENE_BATTLE_NPC_OWER_NOT_FOUND`；含义：ERR / 场景 / 战斗 / NPC / OWER / NOT / FOUND，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51309：`ERR_SCENE_BATTLE_NPC_DUPLI_FIGHT`；含义：ERR / 场景 / 战斗 / NPC / DUPLI / FIGHT，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.SceneErr` 新增数值 51318：`ERR_SCENE_AVATAR_NOT_IN_TRANSFORM`；含义：ERR / 场景 / 角色 / NOT / IN / 变身，属于 MOBA_RET.SceneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 2408：`ERR_ZONE_TASK_RECOVER_ALL_IN_CD`；含义：ERR / Zone 服务 / 任务 / RECOVER / ALL / IN / CD，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 2715：`ERR_ZONE_PET_EGG_ADD_HATCH_TIME_OVERFLOW`；含义：ERR / Zone 服务 / 宠物 / EGG / 添加 / HATCH / 时间 / OVERFLOW，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 2865：`ERR_ZONE_PET_BACKTRACK_BASE_ID_INVALID`；含义：ERR / Zone 服务 / 宠物 / BACKTRACK / 基础 / ID / INVALID，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 2866：`ERR_ZONE_PET_BACKTRACK_IS_ALREADY_BACKTRACKED`；含义：ERR / Zone 服务 / 宠物 / BACKTRACK / IS / ALREADY / BACKTRACKED，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 2867：`ERR_ZONE_PET_BACKTRACK_ITEM_IS_EMPTY`；含义：ERR / Zone 服务 / 宠物 / BACKTRACK / 道具 / IS / EMPTY，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3010：`ERR_ZONE_INVALID_LOTTERY_DRAW_PARAM`；含义：ERR / Zone 服务 / INVALID / 抽奖 / 抽取 / PARAM，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3011：`ERR_ZONE_LOTTERY_NO_AVAILABLE_REWARD`；含义：ERR / Zone 服务 / 抽奖 / NO / AVAILABLE / 奖励，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3016：`ERR_ZONE_GLOBAL_CHALLENGE_CONDITION_NOT_MET`；含义：ERR / Zone 服务 / GLOBAL / 挑战 / CONDITION / NOT / MET，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3102：`ERR_ZONE_WEGAME_LOGIN_AUTH_FAILED`；含义：ERR / Zone 服务 / WEGAME / 登录 / AUTH / FAILED，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3200：`ERR_ZONE_PHOTO_CONTEST_OUTSIDE_SUBMISSION`；含义：ERR / Zone 服务 / 照片 / 比赛 / OUTSIDE / SUBMISSION，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3201：`ERR_ZONE_PHOTO_CONTEST_OUTSIDE_SELECTION`；含义：ERR / Zone 服务 / 照片 / 比赛 / OUTSIDE / SELECTION，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3204：`ERR_ZONE_PHOTO_CONTEST_PHASE_NEED_REFRESH`；含义：ERR / Zone 服务 / 照片 / 比赛 / PHASE / NEED / 刷新，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3205：`ERR_ZONE_HANDBOOK_SEASON_AWARD_AGAIN`；含义：ERR / Zone 服务 / 图鉴 / SEASON / AWARD / AGAIN，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3206：`ERR_ZONE_HANDBOOK_SEASON_AWARD_CANT`；含义：ERR / Zone 服务 / 图鉴 / SEASON / AWARD / CANT，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3207：`ERR_ZONE_PHOTO_CONTEST_HOT_PHOTO`；含义：ERR / Zone 服务 / 照片 / 比赛 / 热门 / 照片，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3210：`ERR_ZONE_ACTIVITY_PET_TRIP_SLOT_FULL`；含义：ERR / Zone 服务 / 活动 / 宠物 / 旅行 / SLOT / FULL，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3211：`ERR_ZONE_ACTIVITY_PET_TRIP_PET_NOT_IN_FORMATION`；含义：ERR / Zone 服务 / 活动 / 宠物 / 旅行 / 宠物 / NOT / IN / FORMATION，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3212：`ERR_ZONE_ACTIVITY_PET_TRIP_PET_NOT_FOUND`；含义：ERR / Zone 服务 / 活动 / 宠物 / 旅行 / 宠物 / NOT / FOUND，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3213：`ERR_ZONE_ACTIVITY_PET_TRIP_PET_ALREADY_IN_TRIP`；含义：ERR / Zone 服务 / 活动 / 宠物 / 旅行 / 宠物 / ALREADY / IN / 旅行，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3214：`ERR_ACTIVITY_PET_TRIP_JOY_NOT_ENOUGH`；含义：ERR / 活动 / 宠物 / 旅行 / JOY / NOT / ENOUGH，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3215：`ERR_ZONE_ACTIVITY_PET_TRIP_LOTTERY_NOT_COMPLETE`；含义：ERR / Zone 服务 / 活动 / 宠物 / 旅行 / 抽奖 / NOT / COMPLETE，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3216：`ERR_ZONE_ACTIVITY_PET_TRIP_DRAW_TIME_NOT_REACHED`；含义：ERR / Zone 服务 / 活动 / 宠物 / 旅行 / 抽取 / 时间 / NOT / REACHED，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3217：`ERR_ZONE_ACTIVITY_PET_TRIP_NO_REWARD`；含义：ERR / Zone 服务 / 活动 / 宠物 / 旅行 / NO / 奖励，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3300：`ERR_ZONE_RANKBOARD_LIST_INCOMPLETE`；含义：ERR / Zone 服务 / RANKBOARD / 列表 / INCOMPLETE，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3351：`ERR_ZONE_PHOTO_CONTEST_SUBMIT_CD`；含义：ERR / Zone 服务 / 照片 / 比赛 / SUBMIT / CD，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3352：`ERR_ZONE_PHOTO_CONTEST_REACH_MAX_RECOMMEND`；含义：ERR / Zone 服务 / 照片 / 比赛 / REACH / MAX / 推荐，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3353：`ERR_ZONE_PHOTO_CONTEST_LIKE_TIMEOUT`；含义：ERR / Zone 服务 / 照片 / 比赛 / 点赞 / TIMEOUT，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3354：`ERR_ZONE_PHOTO_CONTEST_ALREADY_LIKED`；含义：ERR / Zone 服务 / 照片 / 比赛 / ALREADY / LIKED，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3355：`ERR_ZONE_PHOTO_CONTEST_REACH_MAX_SKIP`；含义：ERR / Zone 服务 / 照片 / 比赛 / REACH / MAX / SKIP，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3356：`ERR_ZONE_PROCESS_SCENE_CATCH_RESULT_FAIL`；含义：ERR / Zone 服务 / PROCESS / 场景 / CATCH / RESULT / FAIL，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3357：`ERR_ZONE_BP_GIFT_CANT_RECV`；含义：ERR / Zone 服务 / BP / 礼物 / CANT / RECV，属于 MOBA_RET.ZoneErr。
- `errorcode.proto` 中的 `MOBA_RET.ZoneErr` 新增数值 3593：`ERR_ZONE_SET_TRACK_TASK_LIMIT`；含义：ERR / Zone 服务 / 设置 / 跟踪 / 任务 / LIMIT，属于 MOBA_RET.ZoneErr。
- `xls_enum.proto` 中的 `MagicEffect` 新增数值 6：`ME_HYPNOTIZE`；含义：ME / HYPNOTIZE，属于 MagicEffect。
- `xls_enum.proto` 中的 `MapIconShowType` 新增数值 18：`MAP_NPC_SHINING`；含义：MAP / NPC / SHINING，属于 MapIconShowType。
- `xls_enum.proto` 中的 `MapIconShowType` 新增数值 19：`MAP_NPC_SHINING_DAZZLING`；含义：MAP / NPC / SHINING / DAZZLING，属于 MapIconShowType。
- `xls_enum.proto` 中的 `MapIconShowType` 新增数值 20：`MAP_SHINING_SEASON_DAZZLING`；含义：MAP / SHINING / SEASON / DAZZLING，属于 MapIconShowType。
- `xls_enum.proto` 中的 `MapIconShowType` 新增数值 21：`MAP_SHINING_CHAOS`；含义：MAP / SHINING / CHAOS，属于 MapIconShowType。
- `xls_enum.proto` 中的 `MiniGameType` 新增数值 4：`MINIGAME_BOSS_BATTLE`；含义：MINIGAME / BOSS / 战斗，属于 MiniGameType。
- `xls_enum.proto` 中的 `MonsterDifficultyType` 新增数值 28：`MODT_FANYING_BOSS`；含义：MODT / FANYING / BOSS，属于 MonsterDifficultyType。
- `xls_enum.proto` 中的 `MonsterDifficultyType` 新增数值 31：`MODT_JIMUFANGZHOU_BOSS`；含义：MODT / JIMUFANGZHOU / BOSS，属于 MonsterDifficultyType。
- `xls_enum.proto` 中的 `NpcSceneCommandType` 新增数值 16：`NSC_LLM_OVERWRITE_BT`；含义：NSC / LLM / OVERWRITE / BT，属于 NpcSceneCommandType。
- `xls_enum.proto` 中的 `NpcSceneCommandType` 新增数值 17：`NSC_LLM_OVERWRITE_BT_START`；含义：NSC / LLM / OVERWRITE / BT / 开始，属于 NpcSceneCommandType。
- `com_pet.proto` 中的 `PetDataBitFlag` 新增数值 512：`PDBF_PET_HAS_BACKTRACK_SNAPSHOT`；含义：PDBF / 宠物 / HAS / BACKTRACK / SNAPSHOT，属于 PetDataBitFlag。
- `com_pet.proto` 中的 `PetDataBitFlag` 新增数值 1024：`PDBF_PET_HAS_BACKTRACK_ITEMS`；含义：PDBF / 宠物 / HAS / BACKTRACK / ITEMS，属于 PetDataBitFlag。
- `com_pet.proto` 中的 `PetDataBitFlag` 新增数值 2048：`PDBF_PET_IS_FROM_SEASON`；含义：PDBF / 宠物 / IS / FROM / SEASON，属于 PetDataBitFlag。
- `com_pet.proto` 中的 `PetDataBitFlag` 新增数值 8192：`PDBF_PET_AFTER_INIT`；含义：PDBF / 宠物 / AFTER / 初始化，属于 PetDataBitFlag。
- `xls_enum.proto` 中的 `PetEvolutionCondition` 新增数值 22：`PEC_NEED_CAMP`；含义：PEC / NEED / 营地，属于 PetEvolutionCondition。
- `battle_data.proto` 中的 `PetSkillRoundData.FLAG` 新增数值 32768：`FLAG_OBTAINED_IN_CROSS_TRANSFER`；含义：标记 / OBTAINED / IN / CROSS / TRANSFER，属于 PetSkillRoundData.FLAG。
- `battle_data.proto` 中的 `PetSkillRoundData.FLAG` 新增数值 65536：`FLAG_OBTAINED_BY_BUFF_146`；含义：标记 / OBTAINED / BY / Buff / 146，属于 PetSkillRoundData.FLAG。
- `battle_data.proto` 中的 `PetSkillRoundData.FLAG` 新增数值 131072：`FLAG_REMOVED_IN_BUFF_146`；含义：标记 / REMOVED / IN / Buff / 146，属于 PetSkillRoundData.FLAG。
- `battle_data.proto` 中的 `PetSkillRoundData.FLAG` 新增数值 262144：`FLAG_OBTAINED_BY_BUFF_155`；含义：标记 / OBTAINED / BY / Buff / 155，属于 PetSkillRoundData.FLAG。
- `xls_enum.proto` 中的 `PetguardBanFunc` 新增数值 9：`PETGUARD_BAN_INFO_CHANGE`；含义：PETGUARD / BAN / 信息 / 改变，属于 PetguardBanFunc。
- `xls_enum.proto` 中的 `PetguardRequireWay` 新增数值 6：`PETGUARD_INFO_CHANGE`；含义：PETGUARD / 信息 / 改变，属于 PetguardRequireWay。
- `space_data.proto` 中的 `PlayerAttackPerformType` 新增数值 1000：`PAPT_None`；含义：PAPT / None，属于 PlayerAttackPerformType。
- `com_account.proto` 中的 `PlayerBanType` 新增数值 20：`PBT_PhotoContest`；含义：PBT / PhotoContest，属于 PlayerBanType。
- `xls_enum.proto` 中的 `PlayerConditionType` 新增数值 123：`PCT_MARK_MESSAGE_SHARE`；含义：PCT / MARK / 消息 / SHARE，属于 PlayerConditionType。
- `xls_enum.proto` 中的 `PlayerConditionType` 新增数值 124：`PCT_PROP_BLINDBOX`；含义：PCT / PROP / BLINDBOX，属于 PlayerConditionType。
- `xls_enum.proto` 中的 `PlayerConditionType` 新增数值 127：`PCT_ROLEPLAY_EMOTE`；含义：PCT / ROLEPLAY / EMOTE，属于 PlayerConditionType。
- `xls_enum.proto` 中的 `PlayerConditionType` 新增数值 128：`PCT_DOUBLE_RIDE_LEADER`；含义：PCT / DOUBLE / RIDE / LEADER，属于 PlayerConditionType。
- `xls_enum.proto` 中的 `PlayerConditionType` 新增数值 129：`PCT_MARK_VIDEO_SOCIAL_SHARE`；含义：PCT / MARK / 视频 / SOCIAL / SHARE，属于 PlayerConditionType。
- `xls_enum.proto` 中的 `PlayerFunctionBanType` 新增数值 124：`PFBT_RP_DRESSUP`；含义：RP / DRESSUP，属于 玩家功能封禁类型。
- `xls_enum.proto` 中的 `PlayerFunctionBanType` 新增数值 125：`PFBT_END`；含义：旧的功能封禁枚举结束标记。
- `space_data.proto` 中的 `PlayerPerformType` 新增数值 10：`PPT_PHOTO_ANIM`；含义：PPT / 照片 / ANIM，属于 PlayerPerformType。
- `com_player.proto` 中的 `PlayerPhotoAlbumType` 新增数值 3：`PLAYER_PHOTO_ALBUM_TYPE_ACT_TAKE_PHOTO`；含义：玩家 / 照片 / ALBUM / TYPE / ACT / TAKE / 照片，属于 PlayerPhotoAlbumType。
- `xls_enum.proto` 中的 `PlayerStoryFlagEnum` 新增数值 1534：`PSF_FRIEND_TELEBAN_JIMUFANGZHOUMAXITUAN`；含义：PSF / 好友 / TELEBAN / JIMUFANGZHOUMAXITUAN，属于 PlayerStoryFlagEnum。
- `xls_enum.proto` 中的 `PlayerStoryFlagEnum` 新增数值 5000：`PSF_DIA_PETLEADER_FARR_MEMENTO`；含义：PSF / DIA / PETLEADER / FARR / MEMENTO，属于 PlayerStoryFlagEnum。
- `xls_enum.proto` 中的 `PlayerStoryFlagEnum` 新增数值 5001：`PSF_DIA_PETLEADER_ATLAN_MEMENTO`；含义：PSF / DIA / PETLEADER / ATLAN / MEMENTO，属于 PlayerStoryFlagEnum。
- `xls_enum.proto` 中的 `PlayerStoryFlagEnum` 新增数值 5002：`PSF_DIA_PETLEADER_FUMORGAN_MEMENTO`；含义：PSF / DIA / PETLEADER / FUMORGAN / MEMENTO，属于 PlayerStoryFlagEnum。
- `xls_enum.proto` 中的 `PlayerStoryFlagEnum` 新增数值 5003：`PSF_DIA_PETLEADER_ARYA_MEMENTO`；含义：PSF / DIA / PETLEADER / ARYA / MEMENTO，属于 PlayerStoryFlagEnum。
- `xls_enum.proto` 中的 `PlayerStoryFlagEnum` 新增数值 5004：`PSF_DIA_PETLEADER_BLACK_MEMENTO`；含义：PSF / DIA / PETLEADER / BLACK / MEMENTO，属于 PlayerStoryFlagEnum。
- `xls_enum.proto` 中的 `PlayerStoryFlagEnum` 新增数值 5007：`PSF_DIA_PETLEADER_DOCT_MEMENTO`；含义：PSF / DIA / PETLEADER / DOCT / MEMENTO，属于 PlayerStoryFlagEnum。
- `xls_enum.proto` 中的 `PlayerStoryFlagEnum` 新增数值 9919：`PSF_FUNC_SEASON02_TELEPORT`；含义：PSF / FUNC / SEASON02 / 传送，属于 PlayerStoryFlagEnum。
- `xls_enum.proto` 中的 `PlayerStoryFlagEnum` 新增数值 100012：`PSF_OPT_GRASSTRIAL`；含义：PSF / OPT / GRASSTRIAL，属于 PlayerStoryFlagEnum。
- `xls_enum.proto` 中的 `PlayerStoryFlagEnum` 新增数值 100021：`PSF_OPT_TRANSFORM_KRITHIA`；含义：PSF / OPT / 变身 / KRITHIA，属于 PlayerStoryFlagEnum。
- `xls_enum.proto` 中的 `PlayerStoryFlagEnum` 新增数值 100022：`PSF_OPT_TRANSFORM_FURTH`；含义：PSF / OPT / 变身 / FURTH，属于 PlayerStoryFlagEnum。
- `xls_enum.proto` 中的 `PlayerStoryFlagEnum` 新增数值 100023：`PSF_OPT_TRANSFORM_DREAM`；含义：PSF / OPT / 变身 / DREAM，属于 PlayerStoryFlagEnum。
- `com_action.proto` 中的 `PlayerTransformCancelReason` 新增数值 13：`PTCR_PLAYER_LOGOUT`；含义：PTCR / 玩家 / 登出，属于 PlayerTransformCancelReason。
- `com_action.proto` 中的 `PlayerTransformCancelReason` 新增数值 15：`PTCR_EAGLE_HIT_CHICKEN`；含义：PTCR / 鹰 / 命中 / CHICKEN，属于 PlayerTransformCancelReason。
- `com_action.proto` 中的 `PlayerTransformCancelReason` 新增数值 16：`PTCR_EAGLE_CHICKEN_ACTIVITY_FINISH`；含义：PTCR / 鹰 / CHICKEN / 活动 / 完成，属于 PlayerTransformCancelReason。
- `xls_enum.proto` 中的 `PreciousEggType` 新增数值 8：`PET_CHAOS`；含义：宠物 / CHAOS，属于 PreciousEggType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 89：`RPBT_RELAX_HUANYINGLINGGU`；含义：RPBT / RELAX / HUANYINGLINGGU，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 90：`RPBT_RELAX_BUKUGU`；含义：RPBT / RELAX / BUKUGU，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 91：`RPBT_RELAX_LIULANGSHU`；含义：RPBT / RELAX / LIULANGSHU，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 92：`RPBT_SEEK`；含义：RPBT / SEEK，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 93：`RPBT_SHH`；含义：RPBT / SHH，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 94：`RPBT_NO`；含义：RPBT / NO，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 95：`RPBT_CLAP`；含义：RPBT / CLAP，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 96：`RPBT_SEEK_2`；含义：RPBT / SEEK / 2，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 97：`RPBT_SHH_2`；含义：RPBT / SHH / 2，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 98：`RPBT_NO_2`；含义：RPBT / NO / 2，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 99：`RPBT_CLAP_2`；含义：RPBT / CLAP / 2，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 100：`RPBT_RELAX_HAIBAOCHUANZHANG`；含义：RPBT / RELAX / HAIBAOCHUANZHANG，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 101：`RPBT_RELAX_QIANJIKUI`；含义：RPBT / RELAX / QIANJIKUI，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 102：`RPBT_RELAX_MIMIXIANGGUAI`；含义：RPBT / RELAX / MIMIXIANGGUAI，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 103：`RPBT_RELAX_SHUOYEYIFU`；含义：RPBT / RELAX / SHUOYEYIFU，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 104：`RPBT_RELAX_WULATA`；含义：RPBT / RELAX / WULATA，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 105：`RPBT_PROP_BLINDBOX`；含义：RPBT / PROP / BLINDBOX，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 106：`RPBT_PROP_STARPILLOW`；含义：RPBT / PROP / STARPILLOW，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 107：`RPBT_PROP_PUMPKINCHAIR`；含义：RPBT / PROP / PUMPKINCHAIR，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 108：`RPBT_RELAX_QIUKA`；含义：RPBT / RELAX / QIUKA，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 109：`RPBT_THANKS`；含义：RPBT / THANKS，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RPBehaviorType` 新增数值 110：`RPBT_THANKS_2`；含义：RPBT / THANKS / 2，属于 RPBehaviorType。
- `xls_enum.proto` 中的 `RankListType` 新增数值 4：`RANK_LIST_TYPE_PHOTO_CONTEST`；含义：排行榜 / 列表 / TYPE / 照片 / 比赛，属于 RankListType。
- `xls_enum.proto` 中的 `RedPointReason` 新增数值 109：`RPR_LEGEND_ALL_FINISH_TOPIC`；含义：RPR / LEGEND / ALL / 完成 / TOPIC，属于 RedPointReason。
- `xls_enum.proto` 中的 `RedPointReason` 新增数值 110：`RPR_LEGEND_SEASON_PHOTO_FINISH`；含义：RPR / LEGEND / SEASON / 照片 / 完成，属于 RedPointReason。
- `xls_enum.proto` 中的 `RedPointReason` 新增数值 178：`RPR_TAKEPHOTO_COMPETITION_JUDGE`；含义：RPR / 拍照 / 比赛 / 判定，属于 RedPointReason。
- `xls_enum.proto` 中的 `RedPointReason` 新增数值 179：`RPR_ACTIVITY_RECALL_BP_TASK_REWARD`；含义：RPR / 活动 / 回流 / BP / 任务 / 奖励，属于 RedPointReason。
- `xls_enum.proto` 中的 `RedPointReason` 新增数值 180：`RPR_ACTIVITY_RECALL_TAB_NOTIFY`；含义：RPR / 活动 / 回流 / TAB / 通知，属于 RedPointReason。
- `xls_enum.proto` 中的 `RedPointReason` 新增数值 181：`RPR_PET_TRIP_NONE`；含义：RPR / 宠物 / 旅行 / NONE，属于 RedPointReason。
- `xls_enum.proto` 中的 `RedPointReason` 新增数值 182：`RPR_PET_TRIP_AWARD`；含义：RPR / 宠物 / 旅行 / AWARD，属于 RedPointReason。
- `xls_enum.proto` 中的 `RedPointReason` 新增数值 183：`RPR_PET_TRIP_GIFT`；含义：RPR / 宠物 / 旅行 / 礼物，属于 RedPointReason。
- `xls_enum.proto` 中的 `RedPointReason` 新增数值 184：`RPR_SEASON_TALENT_ENABLE`；含义：RPR / SEASON / TALENT / 启用，属于 RedPointReason。
- `xls_enum.proto` 中的 `RedPointReason` 新增数值 185：`RPR_ACTIVITY_RECALL_TAB_REWARD`；含义：RPR / 活动 / 回流 / TAB / 奖励，属于 RedPointReason。
- `xls_enum.proto` 中的 `RedPointReason` 新增数值 186：`RPR_AICOACH_FIRST_OPEN`；含义：RPR / AICOACH / FIRST / 开启，属于 RedPointReason。
- `xls_enum.proto` 中的 `RedPointReason` 新增数值 187：`RPR_UNLOCK_CAMERA_SKIN`；含义：RPR / 解锁 / CAMERA / SKIN，属于 RedPointReason。
- `xls_enum.proto` 中的 `RedPointReason` 新增数值 188：`RPR_PRE_DOWNLOAD_REWARD`；含义：RPR / 预 / 下载 / 奖励，属于 RedPointReason。
- `xls_enum.proto` 中的 `RedPointReason` 新增数值 191：`RPR_PRE_DOWNLOAD_START`；含义：RPR / 预 / 下载 / 开始，属于 RedPointReason。
- `xls_enum.proto` 中的 `RefreshRuleConf` 新增数值 451：`RRC_ACTIVITY_KELIJI_4m_RESET`；含义：RRC / 活动 / KELIJI / 4m / RESET，属于 RefreshRuleConf。
- `xls_enum.proto` 中的 `RefreshRuleConf` 新增数值 452：`RRC_ACTIVITY_ZILINGYING_6m_RESET`；含义：RRC / 活动 / ZILINGYING / 6m / RESET，属于 RefreshRuleConf。
- `xls_enum.proto` 中的 `RefreshRuleConf` 新增数值 453：`RRC_ACTIVITY_GUODONG_2m_RESET`；含义：RRC / 活动 / GUODONG / 2m / RESET，属于 RefreshRuleConf。
- `xls_enum.proto` 中的 `RefreshRuleConf` 新增数值 454：`RRC_REWARD_1H_RESET_AI_COLLECT`；含义：RRC / 奖励 / 1H / RESET / AI / COLLECT，属于 RefreshRuleConf。
- `xls_enum.proto` 中的 `RefreshRuleConf` 新增数值 455：`RRC_ACTIVITY_5s_RESET`；含义：RRC / 活动 / 5s / RESET，属于 RefreshRuleConf。
- `xls_enum.proto` 中的 `RefreshRuleConf` 新增数值 456：`RRC_ACTIVITY_1d_RESET_NEW`；含义：RRC / 活动 / 1d / RESET / NEW，属于 RefreshRuleConf。
- `xls_enum.proto` 中的 `RefreshRuleConf` 新增数值 800：`RRC_COLLECTED_22h_RESEST`；含义：RRC / COLLECTED / 22h / RESEST，属于 RefreshRuleConf。
- `xls_enum.proto` 中的 `RefreshRuleConf` 新增数值 801：`RRC_COLLECTED_30m_ALLWEATHER_NIGHT_RESEST`；含义：RRC / COLLECTED / 30m / ALLWEATHER / NIGHT / RESEST，属于 RefreshRuleConf。
- `xls_enum.proto` 中的 `ReleaseBattleReason` 新增数值 7：`RBR_CREATE_BATTLE_FAILED`；含义：RBR / CREATE / 战斗 / FAILED，属于 ReleaseBattleReason。
- `com_actor.proto` 中的 `RemoveAuraReason` 新增数值 6：`DAR_AOI`；含义：DAR / AOI，属于 RemoveAuraReason。
- `xls_enum.proto` 中的 `ReportCoinRatio` 新增数值 6：`RCR_BLOOD`；含义：RCR / BLOOD，属于 ReportCoinRatio。
- `xls_enum.proto` 中的 `RewardTag` 新增数值 8：`RTA_ACTIVITY_FLOWER_MEDAL`；含义：RTA / 活动 / FLOWER / MEDAL，属于 RewardTag。
- `xls_enum.proto` 中的 `RewardTag` 新增数值 9：`RTA_ACTIVITY_FLOWER_FIRST`；含义：RTA / 活动 / FLOWER / FIRST，属于 RewardTag。
- `xls_enum.proto` 中的 `RidePetPassiveSkillType` 新增数值 6：`RPPST_Resonance`；含义：RPPST / Resonance，属于 RidePetPassiveSkillType。
- `scene_notify.proto` 中的 `STAMINA_CHANGE_REASON` 新增数值 5：`SCR_TEMP_RIDE`；含义：SCR / 临时 / RIDE，属于 STAMINA_CHANGE_REASON。
- `com_account.proto` 中的 `SafetyBusinessInfo.ReportCategory` 新增数值 8：`RPTCAT_CUSTOM_CONTENT`；含义：RPTCAT / CUSTOM / 内容，属于 SafetyBusinessInfo.ReportCategory。
- `com_account.proto` 中的 `SafetyBusinessInfo.ReportReason` 新增数值 793：`RPTRS_NON_GAMING_PHOTOS`；含义：RPTRS / NON / GAMING / PHOTOS，属于 SafetyBusinessInfo.ReportReason。
- `xls_enum.proto` 中的 `SceneAbilityDisableCode` 新增数值 8：`SADC_HOME`；含义：场景能力在家园中禁用。
- `xls_enum.proto` 中的 `SceneEventType` 新增数值 4：`SET_CONTINUOUS_CATCH_BOX`；含义：设置 / CONTINUOUS / CATCH / 盒子，属于 SceneEventType。
- `xls_enum.proto` 中的 `SceneEventType` 新增数值 5：`SET_CONTINUOUS_CATCH_BOXEVENT`；含义：设置 / CONTINUOUS / CATCH / BOXEVENT，属于 SceneEventType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 55：`SGT_DEBUG_DRAW_AIR_WALL`；含义：SGT / DEBUG / 抽取 / AIR / 墙面，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 56：`SGT_FINISH_SPEC_BATTLE`；含义：SGT / 完成 / SPEC / 战斗，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 57：`SGT_DEBUG_RAYCAST_WITH_FILTER`；含义：SGT / DEBUG / RAYCAST / WITH / FILTER，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 58：`SGT_DEBUG_OVERLAP_WITH_FILTER`；含义：SGT / DEBUG / OVERLAP / WITH / FILTER，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 59：`SGT_DEBUG_SAMPLE_ENV_IN_RANGE`；含义：SGT / DEBUG / SAMPLE / ENV / IN / RANGE，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 60：`SGT_DEBUG_FIX_POS_TO_STAND`；含义：SGT / DEBUG / FIX / 位置 / 到 / STAND，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 61：`SGT_DEBUG_MAP_MARK_BY_LAYER`；含义：SGT / DEBUG / MAP / MARK / BY / LAYER，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 62：`SGT_DEBUG_GET_CUR_POS_ENV_TYPE`；含义：SGT / DEBUG / 获取 / CUR / 位置 / ENV / TYPE，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 63：`SGT_DEBUG_BONUS_CATCH_RANDOM_POS`；含义：SGT / DEBUG / BONUS / CATCH / RANDOM / 位置，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 64：`SGT_DEBUG_LIGHT_PK`；含义：SGT / DEBUG / LIGHT / PK，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 65：`SGT_LLM_DEBUG`；含义：SGT / LLM / DEBUG，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 66：`SGT_SET_CLIENT_VERSION`；含义：SGT / 设置 / 客户端 / VERSION，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 67：`SGT_SET_NPC_GUARD_DATA`；含义：SGT / 设置 / NPC / GUARD / 数据，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 68：`SGT_ABNORMAL_STATUS`；含义：SGT / ABNORMAL / 状态，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 69：`SGT_SET_CATCH_PROBABILITY`；含义：SGT / 设置 / CATCH / PROBABILITY，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 74：`SGT_DEBUG_BONUS_CATCH_RANDOM_POSV2`；含义：SGT / DEBUG / BONUS / CATCH / RANDOM / POSV2，属于 SceneGmType。
- `com_gm.proto` 中的 `SceneGmType` 新增数值 75：`SGT_GM_SET_SELECT_DATA`；含义：SGT / GM / 设置 / 选择 / 数据，属于 SceneGmType。
- `xls_enum.proto` 中的 `ScenePlayerRideSocketType` 新增数值 22：`G5`；含义：G5，属于 ScenePlayerRideSocketType。
- `xls_enum.proto` 中的 `SceneRideAllActiveType` 新增数值 15：`SRAA_KEEP_BALANCE`；含义：SRAA / KEEP / BALANCE，属于 SceneRideAllActiveType。
- `xls_enum.proto` 中的 `SceneRideAllActiveType` 新增数值 16：`SRAA_DASH_WITHOUT_VITALITY`；含义：SRAA / DASH / WITHOUT / VITALITY，属于 SceneRideAllActiveType。
- `xls_enum.proto` 中的 `SceneRideAllActiveType` 新增数值 17：`SRAA_DASH_DASHFORWARD`；含义：SRAA / DASH / DASHFORWARD，属于 SceneRideAllActiveType。
- `xls_enum.proto` 中的 `SceneRideAllActiveType` 新增数值 18：`SRAA_VERTICAL_FLY`；含义：SRAA / VERTICAL / FLY，属于 SceneRideAllActiveType。
- `xls_enum.proto` 中的 `SceneRideAllActiveType` 新增数值 19：`SRAA_SMASH`；含义：SRAA / SMASH，属于 SceneRideAllActiveType。
- `xls_enum.proto` 中的 `SceneRideAllCustomGid` 新增数值 7：`SRCG_Interact`；含义：SRCG / Interact，属于 SceneRideAllCustomGid。
- `xls_enum.proto` 中的 `SceneRideAllType` 新增数值 15：`SRAT_KEEP_BALANCE`；含义：SRAT / KEEP / BALANCE，属于 SceneRideAllType。
- `xls_enum.proto` 中的 `SelectMarkYellow` 新增数值 14：`SMY_UNCLICKED`；含义：SMY / UNCLICKED，属于 SelectMarkYellow。
- `com_debug_draw.proto` 中的 `ServerDebugDrawType` 新增数值 17：`DRAW_BONUS_CATCH_RANDOM_POS`；含义：抽取 / BONUS / CATCH / RANDOM / 位置，属于 ServerDebugDrawType。
- `xls_enum.proto` 中的 `ShareButtonType` 新增数值 8：`SBT_HB_PHOTO`；含义：SBT / HB / 照片，属于 ShareButtonType。
- `xls_enum.proto` 中的 `ShareButtonType` 新增数值 9：`SBT_RECORD_VIDEO`；含义：SBT / RECORD / 视频，属于 ShareButtonType。
- `space_action.proto` 中的 `SpaceAct_SetNpcPosReason` 新增数值 7：`SNPR_MOVER_RESET_POS`；含义：SNPR / MOVER / RESET / 位置，属于 SpaceAct_SetNpcPosReason。
- `space_action.proto` 中的 `SpaceAct_SetNpcPosReason` 新增数值 8：`SNPR_RELOCATE`；含义：SNPR / RELOCATE，属于 SpaceAct_SetNpcPosReason。
- `space_action.proto` 中的 `SpaceActionType.ENUM` 新增数值 114：`AIMutualPerformStateChanged`；含义：AIMutualPerformStateChanged，属于 SpaceActionType.ENUM。
- `space_action.proto` 中的 `SpaceActionType.ENUM` 新增数值 266：`PlayChatBubble`；含义：PlayChatBubble，属于 SpaceActionType.ENUM。
- `space_action.proto` 中的 `SpaceActionType.ENUM` 新增数值 267：`PlayerTagsChange`；含义：PlayerTagsChange，属于 SpaceActionType.ENUM。
- `space_action.proto` 中的 `SpaceActionType.ENUM` 新增数值 268：`AbnormalStatusChangeNtf`；含义：AbnormalStatusChangeNtf，属于 SpaceActionType.ENUM。
- `space_action.proto` 中的 `SpaceActionType.ENUM` 新增数值 269：`BonusCatchLimitTips`；含义：BonusCatchLimitTips，属于 SpaceActionType.ENUM。
- `space_action.proto` 中的 `SpaceActionType.ENUM` 新增数值 500：`LLM_PETS_QueryPets`；含义：LLM / PETS / QueryPets，属于 SpaceActionType.ENUM。
- `space_action.proto` 中的 `SpaceActionType.ENUM` 新增数值 501：`LLM_PETS_BehaviorNotify`；含义：LLM / PETS / BehaviorNotify，属于 SpaceActionType.ENUM。
- `space_action.proto` 中的 `SpaceActionType.ENUM` 新增数值 502：`LLM_Debug`；含义：LLM / Debug，属于 SpaceActionType.ENUM。
- `space_action.proto` 中的 `SpaceActionType.ENUM` 新增数值 510：`NpcSizeScaleChange`；含义：NpcSizeScaleChange，属于 SpaceActionType.ENUM。
- `space_action.proto` 中的 `SpaceActionType.ENUM` 新增数值 511：`RoleplayPropSlotInfoChg`；含义：RoleplayPropSlotInfoChg，属于 SpaceActionType.ENUM。
- `space_action.proto` 中的 `SpaceActionType.ENUM` 新增数值 512：`OptionBlackOrWhiteListUinsInfoChg`；含义：OptionBlackOrWhiteListUinsInfoChg，属于 SpaceActionType.ENUM。
- `space_action.proto` 中的 `SpaceActionType.ENUM` 新增数值 513：`CameraSkinChange`；含义：CameraSkinChange，属于 SpaceActionType.ENUM。
- `space_action.proto` 中的 `SpaceActionType.ENUM` 新增数值 515：`NpcMutationInfoChange`；含义：NpcMutationInfoChange，属于 SpaceActionType.ENUM。
- `xls_enum.proto` 中的 `SpaceActorLogicStatus` 新增数值 67：`SALS_BLINDBOX_OCCUPIED`；含义：SALS / BLINDBOX / OCCUPIED，属于 SpaceActorLogicStatus。
- `xls_enum.proto` 中的 `SpaceActorLogicStatus` 新增数值 68：`SALS_PLAYER_IN_BLINDBOX`；含义：SALS / 玩家 / IN / BLINDBOX，属于 SpaceActorLogicStatus。
- `xls_enum.proto` 中的 `SpaceActorLogicStatus` 新增数值 69：`SALS_ABNORMALSTATUS`；含义：SALS / ABNORMALSTATUS，属于 SpaceActorLogicStatus。
- `xls_enum.proto` 中的 `SpaceActorLogicStatus` 新增数值 73：`SALS_DOUBLE_RIDE_LEADER`；含义：SALS / DOUBLE / RIDE / LEADER，属于 SpaceActorLogicStatus。
- `xls_enum.proto` 中的 `SpaceActorLogicStatus` 新增数值 1047：`SALS_HIGHBOX_ELITE`；含义：SALS / HIGHBOX / ELITE，属于 SpaceActorLogicStatus。
- `xls_enum.proto` 中的 `SpaceActorLogicStatus` 新增数值 1048：`SALS_MIDBOX_ELITE`；含义：SALS / MIDBOX / ELITE，属于 SpaceActorLogicStatus。
- `xls_enum.proto` 中的 `SpaceActorLogicStatus` 新增数值 1049：`SALS_LOWBOX_ELITE`；含义：SALS / LOWBOX / ELITE，属于 SpaceActorLogicStatus。
- `xls_enum.proto` 中的 `SpaceActorLogicStatus` 新增数值 1050：`SALS_HOME_PET_WAIT_CHECK_IN`；含义：SALS / 家园 / 宠物 / WAIT / 检查 / IN，属于 SpaceActorLogicStatus。
- `xls_enum.proto` 中的 `SpaceActorLogicStatus` 新增数值 1051：`SALS_GRASSTRIAL`；含义：SALS / GRASSTRIAL，属于 SpaceActorLogicStatus。
- `xls_enum.proto` 中的 `SpaceActorLogicStatus` 新增数值 1052：`SALS_HIGH_VALUE_NPC`；含义：SALS / HIGH / VALUE / NPC，属于 SpaceActorLogicStatus。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 21：`SAE_JUESHILU`；含义：SAE / JUESHILU，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 22：`SAE_RUOYANBUDING`；含义：SAE / RUOYANBUDING，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 23：`SAE_BENGBENGHUA`；含义：SAE / BENGBENGHUA，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 24：`SAE_MENGYOUYOU`；含义：SAE / MENGYOUYOU，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 25：`SAE_DIANMIEMIE`；含义：SAE / DIANMIEMIE，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 26：`SAE_XUEYINGWAWA`；含义：SAE / XUEYINGWAWA，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 27：`SAE_YOUMINGYAN`；含义：SAE / YOUMINGYAN，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 28：`SAE_DUDUGUO`；含义：SAE / DUDUGUO，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 29：`SAE_LIULISHUIMU`；含义：SAE / LIULISHUIMU，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 30：`SAE_JIUYOUGU`；含义：SAE / JIUYOUGU，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 31：`SAE_HAIBAOCHUANZHANG`；含义：SAE / HAIBAOCHUANZHANG，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 32：`SAE_QIANJIKUI`；含义：SAE / QIANJIKUI，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 33：`SAE_MIMIXIANGGUAI`；含义：SAE / MIMIXIANGGUAI，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 34：`SAE_GUDEMAOMAO`；含义：SAE / GUDEMAOMAO，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 35：`SAE_JUGUXIANG`；含义：SAE / JUGUXIANG，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 36：`SAE_YANHUABOJUE`；含义：SAE / YANHUABOJUE，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 37：`SAE_XIAOCHOUGONGJUE`；含义：SAE / XIAOCHOUGONGJUE，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 38：`SAE_HUANYINGLINGGU`；含义：SAE / HUANYINGLINGGU，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 39：`SAE_BUKUGU`；含义：SAE / BUKUGU，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 40：`SAE_LIULANGSHU`；含义：SAE / LIULANGSHU，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 41：`SAE_YUANHAOYU`；含义：SAE / YUANHAOYU，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 42：`SAE_BENGCHUANGSONGSHU`；含义：SAE / BENGCHUANGSONGSHU，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 43：`SAE_KAWACHONG`；含义：SAE / KAWACHONG，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitAiEffect` 新增数值 44：`SAE_LILAYAO`；含义：SAE / LILAYAO，属于 SuitAiEffect。
- `xls_enum.proto` 中的 `SuitPrivilegeEffect` 新增数值 4：`SPE_MENGJINGLIULANGZHE`；含义：SPE / MENGJINGLIULANGZHE，属于 SuitPrivilegeEffect。
- `xls_enum.proto` 中的 `TaskClassType` 新增数值 24：`TCT_RECALL_BP`；含义：TCT / 回流 / BP，属于 TaskClassType。
- `xls_enum.proto` 中的 `TaskKeyType` 新增数值 242：`TKT_CHECK_VERSION_NUMBER`；含义：TKT / 检查 / VERSION / NUMBER，属于 TaskKeyType。
- `xls_enum.proto` 中的 `TaskKeyType` 新增数值 378：`TKT_LOTTERY`；含义：TKT / 抽奖，属于 TaskKeyType。
- `xls_enum.proto` 中的 `TaskKeyType` 新增数值 385：`TKT_RECALL_SUB_ACTIVITY_CTRL`；含义：TKT / 回流 / 子 / 活动 / CTRL，属于 TaskKeyType。
- `xls_enum.proto` 中的 `TconndEvHandlerType` 新增数值 4：`TECT_CHANNEL_DIS_INFO_COMP`；含义：TECT / CHANNEL / DIS / 信息 / COMP，属于 TconndEvHandlerType。
- `xls_enum.proto` 中的 `Traverse_Data_Type` 新增数值 4：`TDT_FAKE_MUTATION`；含义：TDT / FAKE / MUTATION，属于 Traverse_Data_Type。
- `xls_enum.proto` 中的 `UIsourceType` 新增数值 15：`UIT_SCAREDBOX`；含义：UIT / SCAREDBOX，属于 UIsourceType。
- `xls_enum.proto` 中的 `VisualItem` 新增数值 51：`VI_ACTIVITY_LEGENDARY_POINTS`；含义：VI / 活动 / LEGENDARY / POINTS，属于 VisualItem。
- `xls_enum.proto` 中的 `VisualItem` 新增数值 53：`VI_RECALLBP_EXP`；含义：VI / RECALLBP / EXP，属于 VisualItem。
- `xls_enum.proto` 中的 `VisualItem` 新增数值 74：`VI_S2_COIN`；含义：VI / S2 / COIN，属于 VisualItem。
- `xls_enum.proto` 中的 `WarehouseUnlockCondition` 新增数值 3：`WUC_USE_BAGITEM`；含义：WUC / 使用 / BAGITEM，属于 WarehouseUnlockCondition。
- `xls_enum.proto` 中的 `WorldBuffEffect` 新增数值 15：`WBE_HP_REDUCE_EXCEPT_RIDING`；含义：WBE / HP / REDUCE / EXCEPT / 骑乘，属于 WorldBuffEffect。
- `com_account.proto` 中的 `WorldIdType` 新增数值 1：`WIDT_OVERSEA`；含义：OVERSEA，属于 世界 ID 类型。
- `xls_enum.proto` 中的 `WorldPlayerStatusType` 新增数值 44：`WPST_FALLOFF`；含义：WPST / FALLOFF，属于 WorldPlayerStatusType。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 653：`ZONE_GET_HANDBOOK_SEASON_AWARD_REQ`；含义：获取 / 图鉴 / SEASON / AWARD / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 654：`ZONE_GET_HANDBOOK_SEASON_AWARD_RSP`；含义：获取 / 图鉴 / SEASON / AWARD / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 790：`ZONE_GET_SELECT_ANOTHER_BATTLE_PASS_THEME_FRIENDS_REQ`；含义：获取 / 选择 / ANOTHER / 战斗 / PASS / THEME / FRIENDS / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 791：`ZONE_GET_SELECT_ANOTHER_BATTLE_PASS_THEME_FRIENDS_RSP`；含义：获取 / 选择 / ANOTHER / 战斗 / PASS / THEME / FRIENDS / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 1167：`ZONE_GET_RANK_USER_REQ`；含义：获取 / 排行榜 / 用户 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 1168：`ZONE_GET_RANK_USER_RSP`；含义：获取 / 排行榜 / 用户 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 1169：`ZONE_GET_RANK_USER_LIST_REQ`；含义：获取 / 排行榜 / 用户 / 列表 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 1170：`ZONE_GET_RANK_USER_LIST_RSP`；含义：获取 / 排行榜 / 用户 / 列表 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 1223：`ZONE_PLAYER_NPC_LOTTERY_GOODS_REWARD_NOTIFY`；含义：玩家 / NPC / 抽奖 / GOODS / 奖励 / 通知，属于 Zone 服务命令号，通知命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 1224：`ZONE_PLAYER_ACTIVITY_DROP_AREA_NOTIFY`；含义：玩家 / 活动 / DROP / 区域 / 通知，属于 Zone 服务命令号，通知命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 4935：`ZONE_GET_PET_INFO_BY_GID_REQ`；含义：获取 / 宠物 / 信息 / BY / GID / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 4936：`ZONE_GET_PET_INFO_BY_GID_RSP`；含义：获取 / 宠物 / 信息 / BY / GID / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6376：`ZONE_ACTIVITY_PHOTO_CONTEST_SUBMIT_REQ`；含义：活动 / 照片 / 比赛 / SUBMIT / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6377：`ZONE_ACTIVITY_PHOTO_CONTEST_SUBMIT_RSP`；含义：活动 / 照片 / 比赛 / SUBMIT / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6378：`ZONE_ACTIVITY_PHOTO_CONTEST_EVALUATION_REQ`；含义：活动 / 照片 / 比赛 / 评审 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6379：`ZONE_ACTIVITY_PHOTO_CONTEST_EVALUATION_RSP`；含义：活动 / 照片 / 比赛 / 评审 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6380：`ZONE_ACTIVITY_PHOTO_CONTEST_LIKE_REQ`；含义：活动 / 照片 / 比赛 / 点赞 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6381：`ZONE_ACTIVITY_PHOTO_CONTEST_LIKE_RSP`；含义：活动 / 照片 / 比赛 / 点赞 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6390：`ZONE_ACTIVITY_SELECT_TRACK_CONTENTS_REQ`；含义：活动 / 选择 / 跟踪 / 内容 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6391：`ZONE_ACTIVITY_SELECT_TRACK_CONTENTS_RSP`；含义：活动 / 选择 / 跟踪 / 内容 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6392：`ZONE_ACTIVITY_POPUP_PLAYED_REQ`；含义：活动 / 弹窗 / PLAYED / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6393：`ZONE_ACTIVITY_POPUP_PLAYED_RSP`；含义：活动 / 弹窗 / PLAYED / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6394：`ZONE_BACKTRACK_PET_REQ`；含义：BACKTRACK / 宠物 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6395：`ZONE_BACKTRACK_PET_RSP`；含义：BACKTRACK / 宠物 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6396：`ZONE_QUERY_BACKTRACK_PET_REWARD_REQ`；含义：查询 / BACKTRACK / 宠物 / 奖励 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6397：`ZONE_QUERY_BACKTRACK_PET_REWARD_RSP`；含义：查询 / BACKTRACK / 宠物 / 奖励 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6400：`ZONE_LLM_PETS_AVAILABLE_PETS_REQ`；含义：LLM / PETS / AVAILABLE / PETS / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6401：`ZONE_LLM_PETS_AVAILABLE_PETS_RSP`；含义：LLM / PETS / AVAILABLE / PETS / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6402：`ZONE_LLM_PETS_BEHAVIOR_REPORT_REQ`；含义：LLM / PETS / BEHAVIOR / 上报 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6403：`ZONE_LLM_PETS_BEHAVIOR_REPORT_RSP`；含义：LLM / PETS / BEHAVIOR / 上报 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6405：`ZONE_ACTIVITY_SAVE_RECOMMEND_PET_TEAM_REQ`；含义：活动 / 保存 / 推荐 / 宠物 / 队伍 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6406：`ZONE_ACTIVITY_SAVE_RECOMMEND_PET_TEAM_RSP`；含义：活动 / 保存 / 推荐 / 宠物 / 队伍 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6407：`ZONE_AI_COACH_SET_STATUS_REQ`；含义：AI / 教练 / 设置 / 状态 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6408：`ZONE_AI_COACH_SET_STATUS_RSP`；含义：AI / 教练 / 设置 / 状态 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6409：`ZONE_AI_COACH_WHITE_LIST_REQ`；含义：AI / 教练 / WHITE / 列表 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6410：`ZONE_AI_COACH_WHITE_LIST_RSP`；含义：AI / 教练 / WHITE / 列表 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6411：`ZONE_AI_COACH_RECOMMEND_LINEUP_REQ`；含义：AI / 教练 / 推荐 / LINEUP / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6412：`ZONE_AI_COACH_RECOMMEND_LINEUP_RSP`；含义：AI / 教练 / 推荐 / LINEUP / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6413：`ZONE_AI_COACH_RECOMMEND_LINEUP_NOTIFY`；含义：AI / 教练 / 推荐 / LINEUP / 通知，属于 Zone 服务命令号，通知命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6414：`ZONE_ACTIVITY_PHOTO_CONTEST_HOT_REQ`；含义：活动 / 照片 / 比赛 / 热门 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6415：`ZONE_ACTIVITY_PHOTO_CONTEST_HOT_RSP`；含义：活动 / 照片 / 比赛 / 热门 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6416：`ZONE_AI_COACH_REQUEST_CANCEL_REQ`；含义：AI / 教练 / REQUEST / 取消 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6417：`ZONE_AI_COACH_REQUEST_CANCEL_RSP`；含义：AI / 教练 / REQUEST / 取消 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6431：`ZONE_ACTIVITY_PHOTO_CONTEST_SUBMIT_REWARD_NOTIFY`；含义：活动 / 照片 / 比赛 / SUBMIT / 奖励 / 通知，属于 Zone 服务命令号，通知命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6432：`ZONE_ACTIVITY_PET_TRIP_ADD_PET_REQ`；含义：活动 / 宠物 / 旅行 / 添加 / 宠物 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6433：`ZONE_ACTIVITY_PET_TRIP_ADD_PET_RSP`；含义：活动 / 宠物 / 旅行 / 添加 / 宠物 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6434：`ZONE_ACTIVITY_PET_TRIP_AUTO_TRIP_REQ`；含义：活动 / 宠物 / 旅行 / 自动 / 旅行 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6435：`ZONE_ACTIVITY_PET_TRIP_AUTO_TRIP_RSP`；含义：活动 / 宠物 / 旅行 / 自动 / 旅行 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6436：`ZONE_ACTIVITY_PET_TRIP_SET_WISH_CHOICE_REQ`；含义：活动 / 宠物 / 旅行 / 设置 / 心愿 / 选择 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6437：`ZONE_ACTIVITY_PET_TRIP_SET_WISH_CHOICE_RSP`；含义：活动 / 宠物 / 旅行 / 设置 / 心愿 / 选择 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6438：`ZONE_ACTIVITY_PET_TRIP_RECEIVE_LOTTERY_REWARD_REQ`；含义：活动 / 宠物 / 旅行 / 领取 / 抽奖 / 奖励 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6439：`ZONE_ACTIVITY_PET_TRIP_RECEIVE_LOTTERY_REWARD_RSP`；含义：活动 / 宠物 / 旅行 / 领取 / 抽奖 / 奖励 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6440：`ZONE_ACTIVITY_PET_TRIP_GET_WISH_CHOICE_COUNT_REQ`；含义：活动 / 宠物 / 旅行 / 获取 / 心愿 / 选择 / 数量 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6441：`ZONE_ACTIVITY_PET_TRIP_GET_WISH_CHOICE_COUNT_RSP`；含义：活动 / 宠物 / 旅行 / 获取 / 心愿 / 选择 / 数量 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6442：`ZONE_RECEIVE_ACTIVITY_RECALL_BP_EXP_REQ`；含义：领取 / 活动 / 回流 / BP / EXP / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6443：`ZONE_RECEIVE_ACTIVITY_RECALL_BP_EXP_RSP`；含义：领取 / 活动 / 回流 / BP / EXP / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6444：`ZONE_RECEIVE_ACTIVITY_RECALL_BP_LEVEL_REWARD_REQ`；含义：领取 / 活动 / 回流 / BP / 等级 / 奖励 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6445：`ZONE_RECEIVE_ACTIVITY_RECALL_BP_LEVEL_REWARD_RSP`；含义：领取 / 活动 / 回流 / BP / 等级 / 奖励 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6446：`ZONE_UNLOCK_ACTIVITY_RECALL_PAID_REWARD_REQ`；含义：解锁 / 活动 / 回流 / 付费 / 奖励 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6447：`ZONE_UNLOCK_ACTIVITY_RECALL_PAID_REWARD_RSP`；含义：解锁 / 活动 / 回流 / 付费 / 奖励 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6448：`ZONE_GET_ACTIVITY_OPTIONAL_PETS_REQ`；含义：获取 / 活动 / 可选 / PETS / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6449：`ZONE_GET_ACTIVITY_OPTIONAL_PETS_RSP`；含义：获取 / 活动 / 可选 / PETS / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6450：`ZONE_ACTIVITY_RECALL_TAG_SWITCH_REQ`；含义：活动 / 回流 / 标签 / 开关 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6451：`ZONE_ACTIVITY_RECALL_TAG_SWITCH_RSP`；含义：活动 / 回流 / 标签 / 开关 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6464：`ZONE_ACTIVITY_PET_TRIP_GET_LOTTERY_RESULT_REQ`；含义：活动 / 宠物 / 旅行 / 获取 / 抽奖 / RESULT / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6465：`ZONE_ACTIVITY_PET_TRIP_GET_LOTTERY_RESULT_RSP`；含义：活动 / 宠物 / 旅行 / 获取 / 抽奖 / RESULT / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6466：`ZONE_PLAYER_BATTLE_PASS_EXP_NOTIFY`；含义：玩家 / 战斗 / PASS / EXP / 通知，属于 Zone 服务命令号，通知命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6467：`ZONE_GET_AREA_ID_REQ`；含义：获取 / 区域 / ID / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6468：`ZONE_GET_AREA_ID_RSP`；含义：获取 / 区域 / ID / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6469：`ZONE_ACTIVITY_PREDOWNLOAD_READY_REQ`；含义：活动 / PREDOWNLOAD / 准备完成 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6470：`ZONE_ACTIVITY_PREDOWNLOAD_READY_RSP`；含义：活动 / PREDOWNLOAD / 准备完成 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6480：`ZONE_GRASS_TRIAL_START_CHALLENGE_REQ`；含义：草系 / 试炼 / 开始 / 挑战 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6481：`ZONE_GRASS_TRIAL_START_CHALLENGE_RSP`；含义：草系 / 试炼 / 开始 / 挑战 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6482：`ZONE_GRASS_TRIAL_ENTER_SCENE_REQ`；含义：草系 / 试炼 / 进入 / 场景 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6483：`ZONE_GRASS_TRIAL_ENTER_SCENE_RSP`；含义：草系 / 试炼 / 进入 / 场景 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6484：`ZONE_SCENE_CREATE_ROLEPLAY_PROP_REQ`；含义：场景 / CREATE / ROLEPLAY / PROP / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6485：`ZONE_SCENE_CREATE_ROLEPLAY_PROP_RSP`；含义：场景 / CREATE / ROLEPLAY / PROP / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6486：`ZONE_SCENE_RECYCLE_ROLEPLAY_PROP_REQ`；含义：场景 / RECYCLE / ROLEPLAY / PROP / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6487：`ZONE_SCENE_RECYCLE_ROLEPLAY_PROP_RSP`；含义：场景 / RECYCLE / ROLEPLAY / PROP / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6488：`ZONE_GRASS_TRIAL_GET_INFO_REQ`；含义：草系 / 试炼 / 获取 / 信息 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6489：`ZONE_GRASS_TRIAL_GET_INFO_RSP`；含义：草系 / 试炼 / 获取 / 信息 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6490：`ZONE_GRASS_TRIAL_ABANDON_CHALLENGE_REQ`；含义：草系 / 试炼 / ABANDON / 挑战 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6491：`ZONE_GRASS_TRIAL_ABANDON_CHALLENGE_RSP`；含义：草系 / 试炼 / ABANDON / 挑战 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6492：`ZONE_GRASS_TRIAL_CHALLENGE_DATA_SYNC_NOTIFY`；含义：草系 / 试炼 / 挑战 / 数据 / 同步 / 通知，属于 Zone 服务命令号，通知命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6493：`ZONE_GRASS_TRIAL_PAUSE_CHALLENGE_REQ`；含义：草系 / 试炼 / PAUSE / 挑战 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6494：`ZONE_GRASS_TRIAL_PAUSE_CHALLENGE_RSP`；含义：草系 / 试炼 / PAUSE / 挑战 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6495：`ZONE_GRASS_TRIAL_RESUME_CHALLENGE_REQ`；含义：草系 / 试炼 / RESUME / 挑战 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6496：`ZONE_GRASS_TRIAL_RESUME_CHALLENGE_RSP`；含义：草系 / 试炼 / RESUME / 挑战 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6497：`ZONE_GRASS_TRIAL_NEXT_NODE_REQ`；含义：草系 / 试炼 / NEXT / 节点 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6498：`ZONE_GRASS_TRIAL_NEXT_NODE_RSP`；含义：草系 / 试炼 / NEXT / 节点 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6499：`ZONE_GRASS_TRIAL_SELECT_EVENT_REQ`；含义：草系 / 试炼 / 选择 / EVENT / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6500：`ZONE_GRASS_TRIAL_SELECT_EVENT_RSP`；含义：草系 / 试炼 / 选择 / EVENT / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6501：`ZONE_GRASS_TRIAL_NODE_REFRESH_REQ`；含义：草系 / 试炼 / 节点 / 刷新 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6502：`ZONE_GRASS_TRIAL_NODE_REFRESH_RSP`；含义：草系 / 试炼 / 节点 / 刷新 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6503：`ZONE_GRASS_TRIAL_HANDLE_REWARD_NOTIFY`；含义：草系 / 试炼 / HANDLE / 奖励 / 通知，属于 Zone 服务命令号，通知命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6504：`ZONE_GRASS_TRIAL_HANDLE_REWARD_REQ`；含义：草系 / 试炼 / HANDLE / 奖励 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6505：`ZONE_GRASS_TRIAL_HANDLE_REWARD_RSP`；含义：草系 / 试炼 / HANDLE / 奖励 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6528：`ZONE_SCENE_CHANGE_NPC_SIZE_SCALE_REQ`；含义：场景 / 改变 / NPC / SIZE / SCALE / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6529：`ZONE_SCENE_CHANGE_NPC_SIZE_SCALE_RSP`；含义：场景 / 改变 / NPC / SIZE / SCALE / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6530：`ZONE_SCENE_THROW_CATCH_FINISH_REQ`；含义：场景 / 投掷 / CATCH / 完成 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6531：`ZONE_SCENE_THROW_CATCH_FINISH_RSP`；含义：场景 / 投掷 / CATCH / 完成 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6532：`ZONE_AI_ATTACK_ABNORMAL_STATUS_REQ`；含义：AI / ATTACK / ABNORMAL / 状态 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6533：`ZONE_AI_ATTACK_ABNORMAL_STATUS_RSP`；含义：AI / ATTACK / ABNORMAL / 状态 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6534：`ZONE_BAG_ITEM_EXPIRE_CONVERT_REQ`；含义：背包 / 道具 / 过期 / 转换 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6535：`ZONE_BAG_ITEM_EXPIRE_CONVERT_RSP`；含义：背包 / 道具 / 过期 / 转换 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6536：`ZONE_BAG_ITEM_EXPIRE_CHECK_REQ`；含义：背包 / 道具 / 过期 / 检查 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6537：`ZONE_BAG_ITEM_EXPIRE_CHECK_RSP`；含义：背包 / 道具 / 过期 / 检查 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6570：`ZONE_GET_DISTRIBUTE_BILL_REQ`；含义：获取 / 分发 / 账单 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6571：`ZONE_GET_DISTRIBUTE_BILL_RSP`；含义：获取 / 分发 / 账单 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6572：`ZONE_DISTRIBUTE_BILL_NOTIFY`；含义：分发 / 账单 / 通知，属于 Zone 服务命令号，通知命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6573：`ZONE_REPORT_DISTRIBUTE_REQ`；含义：上报 / 分发 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6574：`ZONE_REPORT_DISTRIBUTE_RSP`；含义：上报 / 分发 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6575：`ZONE_RPT_MONTH_CARD_TIPS_SHOW_REQ`；含义：RPT / 月 / 卡牌 / 提示 / 展示 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 新增数值 6576：`ZONE_RPT_MONTH_CARD_TIPS_SHOW_RSP`；含义：RPT / 月 / 卡牌 / 提示 / 展示 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd` 新增数值 61694：`ZONE_GM_LLM_PETS_BEHAVIOR_EVAL_REQ`；含义：GM / LLM / PETS / BEHAVIOR / EVAL / 请求，属于 ZoneSvrGmCmd。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd` 新增数值 61695：`ZONE_GM_LLM_PETS_BEHAVIOR_EVAL_RSP`；含义：GM / LLM / PETS / BEHAVIOR / EVAL / 响应，属于 ZoneSvrGmCmd。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd` 新增数值 61700：`ZONE_GM_SET_GLOBAL_CHALLENGE_PROGRESS_REQ`；含义：GM / 设置 / GLOBAL / 挑战 / PROGRESS / 请求，属于 ZoneSvrGmCmd。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd` 新增数值 61701：`ZONE_GM_SET_GLOBAL_CHALLENGE_PROGRESS_RSP`；含义：GM / 设置 / GLOBAL / 挑战 / PROGRESS / 响应，属于 ZoneSvrGmCmd。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd` 新增数值 61702：`ZONE_GM_EXEC_CLIENT_GM_REQ`；含义：GM / EXEC / 客户端 / GM / 请求，属于 ZoneSvrGmCmd。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd` 新增数值 61703：`ZONE_GM_EXEC_CLIENT_GM_RSP`；含义：GM / EXEC / 客户端 / GM / 响应，属于 ZoneSvrGmCmd。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd` 新增数值 61704：`ZONE_GM_CLIENT_NOTIFY`；含义：GM / 客户端 / 通知，属于 ZoneSvrGmCmd。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd` 新增数值 61705：`ZONE_GM_CLIENT_RESPONSE_REQ`；含义：GM / 客户端 / RESPONSE / 请求，属于 ZoneSvrGmCmd。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd` 新增数值 61706：`ZONE_GM_CLIENT_RESPONSE_RSP`；含义：GM / 客户端 / RESPONSE / 响应，属于 ZoneSvrGmCmd。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd` 新增数值 61707：`ZONE_GM_ADD_TEST_SUGGESTION_PLAYERS_REQ`；含义：GM / 添加 / TEST / SUGGESTION / PLAYERS / 请求，属于 ZoneSvrGmCmd。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd` 新增数值 61708：`ZONE_GM_ADD_TEST_SUGGESTION_PLAYERS_RSP`；含义：GM / 添加 / TEST / SUGGESTION / PLAYERS / 响应，属于 ZoneSvrGmCmd。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd` 新增数值 61709：`ZONE_GM_CLEAR_DUNGEON_REQ`；含义：GM / 清理 / 副本 / 请求，属于 ZoneSvrGmCmd。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd` 新增数值 61710：`ZONE_GM_CLEAR_DUNGEON_RSP`；含义：GM / 清理 / 副本 / 响应，属于 ZoneSvrGmCmd。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd` 新增数值 61713：`ZONE_GM_DISTR_GOODS_REQ`；含义：GM / DISTR / GOODS / 请求，属于 ZoneSvrGmCmd。
- `c2s_cmd.proto` 中的 `ZoneSvrGmCmd` 新增数值 61714：`ZONE_GM_DISTR_GOODS_RSP`；含义：GM / DISTR / GOODS / 响应，属于 ZoneSvrGmCmd。

### 删除枚举值
- `xls_enum.proto` 中的 `SceneAbilityDisableCode` 删除数值 3：`SADC_HOME`；含义：场景能力在家园中禁用。
- `com_account.proto` 中的 `WorldIdType` 删除数值 3：`WIDT_OTHER`；含义：其他世界 ID 类型。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 261：`ZONE_LOGOUT_REQ`；含义：登出 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 262：`ZONE_LOGOUT_RSP`；含义：登出 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 289：`ZONE_HEARTBEAT_REQ`；含义：心跳 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 290：`ZONE_HEARTBEAT_RSP`；含义：心跳 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 341：`ZONE_SCENE_CAST_SCENE_SKILL_REQ`；含义：场景 / 施放 / 场景 / 技能 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 342：`ZONE_SCENE_CAST_SCENE_SKILL_RSP`；含义：场景 / 施放 / 场景 / 技能 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 361：`ZONE_MODIFY_BAG_LIST_SORT_REQ`；含义：MODIFY / 背包 / 列表 / 排序 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 362：`ZONE_MODIFY_BAG_LIST_SORT_RSP`；含义：MODIFY / 背包 / 列表 / 排序 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 387：`ZONE_PET_USE_BAG_ITEM_REQ`；含义：宠物 / 使用 / 背包 / 道具 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 388：`ZONE_PET_USE_BAG_ITEM_RSP`；含义：宠物 / 使用 / 背包 / 道具 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 389：`ZONE_PET_BASE_POINT_ASSIGN_REQ`；含义：宠物 / 基础 / 点数 / 分配 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 390：`ZONE_PET_BASE_POINT_ASSIGN_RSP`；含义：宠物 / 基础 / 点数 / 分配 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 393：`ZONE_PET_SET_FOLLOW_REQ`；含义：宠物 / 设置 / 跟随 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 394：`ZONE_PET_SET_FOLLOW_RSP`；含义：宠物 / 设置 / 跟随 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 397：`ZONE_PET_DELETE_REQ`；含义：宠物 / 删除 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 398：`ZONE_PET_DELETE_RSP`；含义：宠物 / 删除 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 414：`ZONE_TASK_TRACE_REQ`；含义：任务 / 追踪 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 415：`ZONE_TASK_TRACE_RSP`；含义：任务 / 追踪 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 416：`ZONE_SCENE_GENERAL_OP_REQ`；含义：场景 / 通用 / 操作 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 417：`ZONE_SCENE_GENERAL_OP_RSP`；含义：场景 / 通用 / 操作 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 420：`ZONE_SCENE_NPC_BATTLE_SERIES_REQ`；含义：场景 / NPC / 战斗 / 连续 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 421：`ZONE_SCENE_NPC_BATTLE_SERIES_RSP`；含义：场景 / NPC / 战斗 / 连续 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 427：`ZONE_SCENE_SET_BROADCAST_LIMIT_REQ`；含义：场景 / 设置 / BROADCAST / LIMIT / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 428：`ZONE_SCENE_SET_BROADCAST_LIMIT_RSP`；含义：场景 / 设置 / BROADCAST / LIMIT / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 454：`ZONE_TRACK_TASK_NPC_REQ`；含义：跟踪 / 任务 / NPC / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 455：`ZONE_TRACK_TASK_NPC_RSP`；含义：跟踪 / 任务 / NPC / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 464：`ZONE_SCENE_BEGIN_SYNC_WORLD_MAP_INFO_REQ`；含义：场景 / 开始 / 同步 / 大世界 / MAP / 信息 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 465：`ZONE_SCENE_BEGIN_SYNC_WORLD_MAP_INFO_RSP`；含义：场景 / 开始 / 同步 / 大世界 / MAP / 信息 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 466：`ZONE_SCENE_END_SYNC_WORLD_MAP_INFO_REQ`；含义：场景 / 结束 / 同步 / 大世界 / MAP / 信息 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 467：`ZONE_SCENE_END_SYNC_WORLD_MAP_INFO_RSP`；含义：场景 / 结束 / 同步 / 大世界 / MAP / 信息 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 468：`ZONE_SCENE_TICK_WORLD_MAP_INFO_SYNC_REQ`；含义：场景 / 周期 / 大世界 / MAP / 信息 / 同步 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 469：`ZONE_SCENE_TICK_WORLD_MAP_INFO_SYNC_RSP`；含义：场景 / 周期 / 大世界 / MAP / 信息 / 同步 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 536：`ZONE_SYNC_TEMP_REQ`；含义：同步 / 临时 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 537：`ZONE_SYNC_TEMP_RSP`；含义：同步 / 临时 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 557：`ZONE_SCENE_THROW_COLLISION_REQ`；含义：场景 / 投掷 / 碰撞 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 558：`ZONE_SCENE_THROW_COLLISION_RSP`；含义：场景 / 投掷 / 碰撞 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 584：`ZONE_BACKPACK_TEAM_UPDATE_REQ`；含义：BACKPACK / 队伍 / 更新 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 585：`ZONE_BACKPACK_TEAM_UPDATE_RSP`；含义：BACKPACK / 队伍 / 更新 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 617：`ZONE_SCENE_CLIENT_VISUALIZATION_REQ`；含义：场景 / 客户端 / VISUALIZATION / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 618：`ZONE_SCENE_CLIENT_VISUALIZATION_RSP`；含义：场景 / 客户端 / VISUALIZATION / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 623：`ZONE_SCENE_CLIENT_VISUALIZATION_NTY`；含义：场景 / 客户端 / VISUALIZATION / 通知，属于 Zone 服务命令号，通知命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 660：`ZONE_SCENE_STRONG_STORM_NTY`；含义：场景 / 强 / 风暴 / 通知，属于 Zone 服务命令号，通知命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 663：`ZONE_TLOG_REPORT_REQ`；含义：TLog 日志 / 上报 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 664：`ZONE_TLOG_REPORT_RSP`；含义：TLog 日志 / 上报 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 712：`ZONE_JUDGE_PAY_REQ`；含义：判定 / 支付 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 713：`ZONE_JUDGE_PAY_RSP`；含义：判定 / 支付 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 714：`ZONE_SCENE_APPLY_VISIT_REQ`；含义：场景 / 申请 / 访问 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 715：`ZONE_SCENE_APPLY_VISIT_RSP`；含义：场景 / 申请 / 访问 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 727：`ZONE_SCENE_APPLY_VISIT_CONFIRM_REQ`；含义：场景 / 申请 / 访问 / 确认 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 728：`ZONE_SCENE_APPLY_VISIT_CONFIRM_RSP`；含义：场景 / 申请 / 访问 / 确认 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 730：`ZONE_SCENE_APPLY_VISIT_LIST_QUERY_REQ`；含义：场景 / 申请 / 访问 / 列表 / 查询 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 731：`ZONE_SCENE_APPLY_VISIT_LIST_QUERY_RSP`；含义：场景 / 申请 / 访问 / 列表 / 查询 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 783：`ZONE_DOTS_COMPONENT_SYNC_REQ`；含义：DOTS / COMPONENT / 同步 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 784：`ZONE_DOTS_COMPONENT_SYNC_RSP`；含义：DOTS / COMPONENT / 同步 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 787：`ZONE_CLEAR_DUNGEON_REQ`；含义：清理 / 副本 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 788：`ZONE_CLEAR_DUNGEON_RSP`；含义：清理 / 副本 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 813：`ZONE_QUERY_ADVENTURE_CHAPTER_REQ`；含义：查询 / 冒险 / 章节 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 814：`ZONE_QUERY_ADVENTURE_CHAPTER_RSP`；含义：查询 / 冒险 / 章节 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 844：`ZONE_SCENE_TEAM_BATTLE_SELECT_FLOWER_BOSS_REQ`；含义：场景 / 队伍 / 战斗 / 选择 / FLOWER / BOSS / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 845：`ZONE_SCENE_TEAM_BATTLE_SELECT_FLOWER_BOSS_RSP`；含义：场景 / 队伍 / 战斗 / 选择 / FLOWER / BOSS / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 864：`ZONE_SCENE_CHANGE_MOVE_MODE_REQ`；含义：场景 / 改变 / 移动 / 模式 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 865：`ZONE_SCENE_CHANGE_MOVE_MODE_RSP`；含义：场景 / 改变 / 移动 / 模式 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 868：`ZONE_GET_SUB_TASK_TOKEN_TRIGGERED_TASK_INFO_REQ`；含义：获取 / 子 / 任务 / token / 触发 / 任务 / 信息 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 869：`ZONE_GET_SUB_TASK_TOKEN_TRIGGERED_TASK_INFO_RSP`；含义：获取 / 子 / 任务 / token / 触发 / 任务 / 信息 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 900：`ZONE_SCENE_WORLD_COMBAT_SKILL_CAST_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 施放 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 901：`ZONE_SCENE_WORLD_COMBAT_SKILL_CAST_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 施放 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 902：`ZONE_SCENE_WORLD_COMBAT_SKILL_SPAWN_NPC_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 生成 / NPC / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 903：`ZONE_SCENE_WORLD_COMBAT_SKILL_SPAWN_NPC_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 生成 / NPC / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 904：`ZONE_SCENE_WORLD_COMBAT_SKILL_SPAWN_BULLET_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 生成 / 子弹 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 905：`ZONE_SCENE_WORLD_COMBAT_SKILL_SPAWN_BULLET_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 生成 / 子弹 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 906：`ZONE_SCENE_WORLD_COMBAT_SKILL_FIRE_BULLET_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 开火 / 子弹 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 907：`ZONE_SCENE_WORLD_COMBAT_SKILL_FIRE_BULLET_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 开火 / 子弹 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 908：`ZONE_SCENE_WORLD_COMBAT_SKILL_BUFF_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / Buff / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 909：`ZONE_SCENE_WORLD_COMBAT_SKILL_BUFF_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / Buff / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 910：`ZONE_SCENE_WORLD_COMBAT_SKILL_END_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 结束 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 911：`ZONE_SCENE_WORLD_COMBAT_SKILL_END_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 结束 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 912：`ZONE_SCENE_WORLD_COMBAT_HIT_REQ`；含义：场景 / 大世界 / COMBAT / 命中 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 913：`ZONE_SCENE_WORLD_COMBAT_HIT_RSP`；含义：场景 / 大世界 / COMBAT / 命中 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 914：`ZONE_CANCEL_TASK_RED_POINT_REQ`；含义：取消 / 任务 / 红点 / 点数 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 915：`ZONE_CANCEL_TASK_RED_POINT_RSP`；含义：取消 / 任务 / 红点 / 点数 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 931：`ZONE_SCENE_WORLD_COMBAT_SKILL_JUMP_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 跳跃 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 932：`ZONE_SCENE_WORLD_COMBAT_SKILL_JUMP_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 跳跃 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 933：`ZONE_SCENE_WORLD_COMBAT_SKILL_JUMP_END_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 跳跃 / 结束 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 934：`ZONE_SCENE_WORLD_COMBAT_SKILL_JUMP_END_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 跳跃 / 结束 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 935：`ZONE_SCENE_WORLD_COMBAT_SKILL_RCD_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / RCD / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 936：`ZONE_SCENE_WORLD_COMBAT_SKILL_RCD_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / RCD / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 937：`ZONE_SCENE_WORLD_COMBAT_SKILL_PET_COLLISION_REQ`；含义：场景 / 大世界 / COMBAT / 技能 / 宠物 / 碰撞 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 938：`ZONE_SCENE_WORLD_COMBAT_SKILL_PET_COLLISION_RSP`；含义：场景 / 大世界 / COMBAT / 技能 / 宠物 / 碰撞 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 973：`ZONE_SCENE_PLAYER_INTERACT_REQ`；含义：场景 / 玩家 / INTERACT / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 974：`ZONE_SCENE_PLAYER_INTERACT_RSP`；含义：场景 / 玩家 / INTERACT / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 975：`ZONE_SCENE_REPLY_PLAYER_INTERACT_REQ`；含义：场景 / REPLY / 玩家 / INTERACT / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 976：`ZONE_SCENE_REPLY_PLAYER_INTERACT_RSP`；含义：场景 / REPLY / 玩家 / INTERACT / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 1004：`ZONE_SCENE_SET_AVATAR_POS_REQ`；含义：场景 / 设置 / 角色 / 位置 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 1005：`ZONE_SCENE_SET_AVATAR_POS_RSP`；含义：场景 / 设置 / 角色 / 位置 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 1024：`ZONE_GET_CAMP_FRUIT_NPC_INFOS_REQ`；含义：获取 / 营地 / 果树 / NPC / INFOS / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 1025：`ZONE_GET_CAMP_FRUIT_NPC_INFOS_RSP`；含义：获取 / 营地 / 果树 / NPC / INFOS / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 1110：`ZONE_TSS_MESSAGE_CHECK_REQ`；含义：安全检查 / 消息 / 检查 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 1111：`ZONE_TSS_MESSAGE_CHECK_RSP`；含义：安全检查 / 消息 / 检查 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 1151：`ZONE_GET_APPEARANCE_INFO_REQ`；含义：获取 / 外观 / 信息 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 1152：`ZONE_GET_APPEARANCE_INFO_RSP`；含义：获取 / 外观 / 信息 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 1180：`ZONE_GET_HANDBOOK_STAT_REQ`；含义：获取 / 图鉴 / 统计 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 1181：`ZONE_GET_HANDBOOK_STAT_RSP`；含义：获取 / 图鉴 / 统计 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5105：`ZONE_BATTLE_ENTER_BATTLE_FIELD_REQ`；含义：战斗 / 进入 / 战斗 / FIELD / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5106：`ZONE_BATTLE_ENTER_BATTLE_FIELD_RSP`；含义：战斗 / 进入 / 战斗 / FIELD / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5145：`ZONE_GET_TASK_SWITCH_DATA_REQ`；含义：获取 / 任务 / 开关 / 数据 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5146：`ZONE_GET_TASK_SWITCH_DATA_RSP`；含义：获取 / 任务 / 开关 / 数据 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5147：`ZONE_CHANGE_TASK_SWITCH_DATA_REQ`；含义：改变 / 任务 / 开关 / 数据 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5148：`ZONE_CHANGE_TASK_SWITCH_DATA_RSP`；含义：改变 / 任务 / 开关 / 数据 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5428：`ZONE_SCENE_HOME_PLANT_CROP_REQ`；含义：场景 / 家园 / PLANT / CROP / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5429：`ZONE_SCENE_HOME_PLANT_CROP_RSP`；含义：场景 / 家园 / PLANT / CROP / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5431：`ZONE_QUERY_SCENE_TASK_STAT_REQ`；含义：查询 / 场景 / 任务 / 统计 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5432：`ZONE_QUERY_SCENE_TASK_STAT_RSP`；含义：查询 / 场景 / 任务 / 统计 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5458：`ZONE_START_BADGE_CHALLENGE_REQ`；含义：开始 / 徽章 / 挑战 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5459：`ZONE_START_BADGE_CHALLENGE_RSP`；含义：开始 / 徽章 / 挑战 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5460：`ZONE_SELECT_BADGE_CHALLENGE_CARD_REQ`；含义：选择 / 徽章 / 挑战 / 卡牌 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5461：`ZONE_SELECT_BADGE_CHALLENGE_CARD_RSP`；含义：选择 / 徽章 / 挑战 / 卡牌 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5462：`ZONE_REFRESH_BADGE_CHALLENGE_CARD_REQ`；含义：刷新 / 徽章 / 挑战 / 卡牌 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5463：`ZONE_REFRESH_BADGE_CHALLENGE_CARD_RSP`；含义：刷新 / 徽章 / 挑战 / 卡牌 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5464：`ZONE_COMBINE_BADGE_CHALLENGE_CARD_REQ`；含义：COMBINE / 徽章 / 挑战 / 卡牌 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5465：`ZONE_COMBINE_BADGE_CHALLENGE_CARD_RSP`；含义：COMBINE / 徽章 / 挑战 / 卡牌 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5466：`ZONE_FIXED_BADGE_CHALLENGE_CARD_REQ`；含义：FIXED / 徽章 / 挑战 / 卡牌 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5467：`ZONE_FIXED_BADGE_CHALLENGE_CARD_RSP`；含义：FIXED / 徽章 / 挑战 / 卡牌 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5468：`ZONE_BADGE_CHALLENGE_SELECT_UPGRADE_REQ`；含义：徽章 / 挑战 / 选择 / UPGRADE / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5469：`ZONE_BADGE_CHALLENGE_SELECT_UPGRADE_RSP`；含义：徽章 / 挑战 / 选择 / UPGRADE / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5470：`ZONE_BADGE_CHALLENGE_ENTER_REQ`；含义：徽章 / 挑战 / 进入 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5471：`ZONE_BADGE_CHALLENGE_ENTER_RSP`；含义：徽章 / 挑战 / 进入 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5506：`ZONE_PET_SHARE_PET_TEAM_REQ`；含义：宠物 / SHARE / 宠物 / 队伍 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5507：`ZONE_PET_SHARE_PET_TEAM_RSP`；含义：宠物 / SHARE / 宠物 / 队伍 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5521：`ZONE_HOME_DB_TEST_REQ`；含义：家园 / DB / TEST / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 5522：`ZONE_HOME_DB_TEST_RSP`；含义：家园 / DB / TEST / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6170：`ZONE_SECONDARY_PASSWORD_CANCEL_FREE_REQ`；含义：二级 / 密码 / 取消 / 免验证 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6171：`ZONE_SECONDARY_PASSWORD_CANCEL_FREE_RSP`；含义：二级 / 密码 / 取消 / 免验证 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6172：`ZONE_SECONDARY_PASSWORD_ACTION_CHECK_REQ`；含义：二级 / 密码 / 行为 / 检查 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6173：`ZONE_SECONDARY_PASSWORD_ACTION_CHECK_RSP`；含义：二级 / 密码 / 行为 / 检查 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6296：`ZONE_VOD_VIDEO_SIGNATURE_REQ`；含义：点播视频 / 视频 / 签名 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6297：`ZONE_VOD_VIDEO_SIGNATURE_RSP`；含义：点播视频 / 视频 / 签名 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6298：`ZONE_PUBLISH_VIDEO_TO_WECHAT_REQ`；含义：发布 / 视频 / 到 / 微信 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6299：`ZONE_PUBLISH_VIDEO_TO_WECHAT_RSP`；含义：发布 / 视频 / 到 / 微信 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6306：`ZONE_POPULARITY_VALUE_REWARD_REQ`；含义：POPULARITY / VALUE / 奖励 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6307：`ZONE_POPULARITY_VALUE_REWARD_RSP`；含义：POPULARITY / VALUE / 奖励 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6332：`ZONE_CHECK_COLOR_SUIT_STATE_REQ`；含义：检查 / 染色 / 套装 / 状态 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6333：`ZONE_CHECK_COLOR_SUIT_STATE_RSP`；含义：检查 / 染色 / 套装 / 状态 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6352：`ZONE_FEED_VIDEO_DEL_UPLOAD_FILE_REQ`；含义：动态 / 视频 / DEL / UPLOAD / FILE / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6353：`ZONE_FEED_VIDEO_DEL_UPLOAD_FILE_RSP`；含义：动态 / 视频 / DEL / UPLOAD / FILE / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6360：`ZONE_GET_CLAIMABLE_GLASS_TINT_REQ`；含义：获取 / 可领取 / 玻璃或镜片 / 染色 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 6361：`ZONE_GET_CLAIMABLE_GLASS_TINT_RSP`；含义：获取 / 可领取 / 玻璃或镜片 / 染色 / 响应，属于 Zone 服务命令号，响应命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 33303：`ZONE_HOME_PET_FOOD_COMPOUND_REQ`；含义：家园 / 宠物 / 食物 / 合成 / 请求，属于 Zone 服务命令号，请求命令。
- `c2s_cmd.proto` 中的 `ZoneSvrCmd` 删除数值 33304：`ZONE_HOME_PET_FOOD_COMPOUND_RSP`；含义：家园 / 宠物 / 食物 / 合成 / 响应，属于 Zone 服务命令号，响应命令。
