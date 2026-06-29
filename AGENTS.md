# AGENTS.md

## Project overview

`orizinarutu-ru` is currently an empty repository. As of this writing it contains
only `README.md` (which holds just the project title) and no application code,
dependencies, tests, or build configuration.

There is intentionally no source code, package manifest (e.g. `package.json`,
`requirements.txt`, `pyproject.toml`, `go.mod`, `Cargo.toml`), lockfile, lint
config, test suite, or build system yet.

## Repository structure

- `README.md` — project title placeholder.
- `AGENTS.md` — this file.

## Conventions

- Branch naming for agent work: use the `cursor/` prefix (e.g.
  `cursor/<descriptive-name>`).
- Commit with clear, descriptive messages; create one commit per logical change.
- Do not force-push or amend commits unless explicitly asked.

## Basic engineering rules for this project

These rules are written for a beginner engineer and should keep day-to-day work
simple, safe, and efficient. Each rule includes a short Japanese explanation so
it is easy to understand why the rule matters.

### Work style

- Start by reading the smallest relevant files before editing.
  - 説明: いきなり広い範囲を触ると、関係ない変更や勘違いが増えます。まず必要な
    ファイルだけを読んで、変更する場所を小さく絞ります。
- Keep each change focused on one purpose.
  - 説明: 1つの変更に複数の目的を混ぜると、レビューや修正が難しくなります。
    「何を直した変更か」が一目で分かる単位にします。
- Prefer simple, readable code over clever code.
  - 説明: 初心者にも読み返せるコードは、将来の修正が楽になります。短すぎる書き方
    や特殊なテクニックより、意味が追いやすい書き方を選びます。
- Use existing project patterns before introducing new tools or structures.
  - 説明: 既存の書き方に合わせると、プロジェクト全体の一貫性が保てます。新しい
    道具や構成は、本当に必要なときだけ追加します。
- When requirements are unclear, write down the assumption in the PR or commit
  message instead of silently guessing.
  - 説明: 不明点を黙って決めると、あとで意図と違う実装になることがあります。
    「こう理解して進めた」と残すことで、確認や修正がしやすくなります。

### Before changing code

- Check `git status` so unrelated user changes are not overwritten.
  - 説明: 作業前に変更済みファイルを確認すると、他の人やユーザーの変更を誤って
    消す事故を防げます。
- Look for an existing script or documented command before inventing a new one.
  - 説明: 既に用意されているコマンドを使う方が、環境差分や手順ミスを減らせます。
    READMEや設定ファイルを先に確認します。
- If adding a new file or dependency, confirm it is necessary for the requested
  task.
  - 説明: ファイルや依存関係を増やすほど管理コストが上がります。目的に対して本当に
    必要なものだけを追加します。
- Avoid broad scaffolding until the project has real source code and a chosen
  stack.
  - 説明: 技術スタックが決まる前に雛形を作ると、不要な構成が残りやすくなります。
    実際の要件が出てから最小限に始めます。

### Quality checks

- Run the narrowest useful check first, then broader checks if the change has
  wider impact.
  - 説明: まず変更箇所に近い確認をすると、問題を早く見つけられます。影響範囲が
    広い場合だけ、全体テストやビルドまで広げます。
- For documentation-only changes, inspect the rendered or plain text result and
  run whitespace checks when possible.
  - 説明: ドキュメント変更でも、読みやすさや余計な空白の確認は必要です。表示や
    差分を見て、意図どおり読めるかを確認します。
- For code changes, run the relevant formatter, linter, tests, and build command
  once those commands exist.
  - 説明: フォーマット、静的チェック、テスト、ビルドはそれぞれ別の問題を見つけます。
    プロジェクトにコマンドが用意されたら、変更内容に合わせて実行します。
- Do not claim a change is verified unless the changed path was actually checked
  by a command, test, or manual review.
  - 説明: 実際に確認していないことを「確認済み」と言うと信頼を失います。何で確認
    したかを説明できる状態にします。

### Efficiency habits

- Keep terminal commands small and repeatable.
  - 説明: 小さいコマンドは失敗時の原因が分かりやすく、同じ手順を再実行しやすいです。
- Prefer project scripts, such as `npm test` or `make test`, once they exist.
  - 説明: プロジェクト用スクリプトは、必要なオプションや前提をまとめてくれます。
    個別コマンドを毎回手入力するよりミスが減ります。
- Reuse common helpers instead of copying logic.
  - 説明: 同じ処理をコピーすると、修正漏れが起きやすくなります。共通の関数や設定が
    ある場合はそれを使います。
- Update documentation when adding a command, setup step, environment variable,
  or workflow that future contributors need.
  - 説明: 自分が追加した手順を残すと、次の作業者が迷いません。セットアップや実行に
    必要な情報はREADMEやこのファイルに追記します。
- Commit one logical change at a time with a message that explains the outcome.
  - 説明: 小さく意味のあるコミットは、あとで履歴を追ったり取り消したりしやすいです。
    メッセージには「何を達成したか」を書きます。

### Learning notes

- When a command fails, read the first actionable error before changing code.
  - 説明: エラー全文を見ずに直すと、原因から外れた変更をしがちです。最初に出ている
    具体的なエラーを読んでから対応します。
- Fix the cause of a problem, not only the visible symptom.
  - 説明: 表面だけ直すと同じ問題が再発します。なぜ起きたかを確認し、原因に対して
    修正します。
- Leave short comments only where the reason is not obvious from the code.
  - 説明: コメントが多すぎると読む量が増えます。コードだけでは理由が伝わりにくい
    場所に、短く補足します。
- If a new pattern is introduced, add a short note here or in the README so it is
  easier to repeat correctly next time.
  - 説明: 新しい書き方や手順は、最初に残しておくとチームの標準になります。次回から
    迷わず同じ品質で作業できます。

## Cursor Cloud specific instructions

- There is nothing to install, lint, test, build, or run yet: no dependency
  manifest or lockfile exists, so there is no development environment to set up.
- Do NOT fabricate a toy application, scaffold a framework, or add dependencies
  just to make setup "pass". Wait until real project code is committed.
- Once actual project code is added (with a manifest/lockfile and source), update
  this file with the concrete commands to install dependencies and to run lint,
  tests, build, and the application in development mode.
