# @kodai-yamamoto-siw/workspace-launch-ui

Docusaurus 用の React フックとボタンコンポーネントです。ドキュメント内から VS Code の `workspace-launch` テンプレートを安全に呼び出すためのユーティリティを提供します。

## インストール

```bash
npm install @kodai-yamamoto-siw/workspace-launch-ui
```

Docusaurus プロジェクトで利用する場合は、併せて以下のピア依存関係が解決されていることを確認してください。

- `react`
- `@docusaurus/router`
- `@docusaurus/useBaseUrl`
- `@docusaurus/Link`
- `@kodai-yamamoto-siw/workspace-template-generator`

## 使い方

```tsx
import WorkspaceLaunchButton, {
  useWorkspaceLaunchUrl,
} from '@kodai-yamamoto-siw/workspace-launch-ui';

const structure = [
  // ...テンプレート構造
];

const href = useWorkspaceLaunchUrl({
  workspaceId: 'my-exercise',
  structure,
});

<WorkspaceLaunchButton workspaceId="my-exercise" structure={structure} />;
```

`useWorkspaceLaunchUrl` はページ URL を元に一意なワークスペース ID を生成し、テンプレートの競合を防ぎます。
