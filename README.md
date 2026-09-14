# 翡翠山 1-2 期别墅小区 · 业主大会公告与竞标材料

本仓库用于向小区业主公开**业主大会公告**与**五家候选物业服务企业的竞标材料**，方便邻居们查阅、下载与比对。

- 公告单位：山河社区居民委员会
- 公示期：2026 年 8 月 28 日 — 9 月 13 日
- 电子投票：2026 年 9 月 15 日 10:00 — 10 月 15 日 10:00（"粤省事"小程序）
- 专有部分建筑总面积 163,230.67 ㎡，总票权 709 票

> 本仓库由业主志愿者整理，**不是官方发布渠道**。一切信息以街镇办（社区居委会）公布的正式文件为准。

## 目录结构

```
index.html                 业主大会公示专页（入口页）
assets/                    页面素材（主视觉、公示件扫描、葵花码）
files/                     公告与五家企业竞标材料原件（PDF）
vote-guide/                "粤省事"投票操作指引（含逐步截图）
```

## 材料清单

| 文件 | 说明 |
| --- | --- |
| 业主大会公告（公示文件）.pdf | 社区居委会公告原件（2 页） |
| 翡翠山物业竞标对比报告.pdf | 五家企业 8 维评分对比报告 |
| 碧桂园物业服务合同.pdf | 含附件一至附件九 |
| 碧桂园物业服务合同(OCR).pdf | 可复制文字版，便于检索 |
| 万科物业服务合同.pdf | — |
| 万科物业翡翠山别墅投标文件（盖章版）.pdf | — |
| 万科物业翡翠山项目物业服务方案（盖章版）.pdf | — |
| 时代物业服务合同.pdf | — |
| 时代邻里--翡翠山1-2期别墅项目物业服务方案（盖章版）.pdf | — |
| 雅居乐（雅生活）物业服务合同（压缩版）.pdf | — |
| 绿维物业服务合同（压缩版）.pdf | — |
| 授权代理人委托书.pdf | 不便本人操作手机时使用 |

## 部署说明

本站为纯静态页面，直接以 GitHub Pages 发布：

- 发布分支：`main`，目录：`/`（根目录）
- `.nojekyll` 用于关闭 Jekyll 处理（中文路径必需）
- 页面已设置 `noindex, nofollow`，避免被搜索引擎收录

## 更新方式

修改 `index.html` 或替换 `files/` 下的材料后：

```bash
git add -A
git commit -m "更新材料"
git push
```

推送后 GitHub Pages 会在 1—2 分钟内自动重新发布。

## 本地推送说明（维护者）

仓库已注册 SSH Deploy Key（写权限），可直接推送。

- 部署私钥：`202608意向合同/.github-pages-deploy/id_ed25519`（与仓库同级，**绝不要提交到任何仓库**）
- 远端地址：`ssh://git@ssh.github.com:443/emeraldhillvilla/public-notice-and-competing-contracts.git`

推送：

    git add -A
    git commit -m "更新材料"
    git push

换机或密钥失效时重新配置：

    git remote set-url origin ssh://git@ssh.github.com:443/emeraldhillvilla/public-notice-and-competing-contracts.git
    git config --local core.sshCommand "ssh -i <私钥路径> -o IdentitiesOnly=yes -o StrictHostKeyChecking=accept-new -o ServerAliveInterval=30"

注意事项

- 本机 `github.com:443`（HTTPS 推送）被网络阻断，统一走 `ssh.github.com:443`。
- 材料合计约 245 MB，建议**分批** `git add` 后推送，单次 30–55 MB 更稳定。
- Windows 上 OpenSSH 会校验私钥权限，若报 `bad permissions`，执行：
  `icacls <私钥路径> /inheritance:r /grant:r "%USERNAME%:R"`
- 单文件超过 50 MB 时 GitHub 会给出告警（不阻断）；超过 100 MB 会被拒收。
