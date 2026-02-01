---
applyTo: '**/*.tsx,**/*.css'
---

# Tailwind CSS v4 構文ガイドライン

このプロジェクトは **Tailwind CSS v4** を使用しています。
レビューやコーディング時は、v4の構文を推奨してください。

## CSS変数の参照構文

### 推奨: v4 簡潔構文

```tsx
// ✅ 推奨: 括弧 () を使用
<div className="bg-(--my-color)" />
<div className="text-(--text-color)" />
<div className="border-(--border-color)" />
<div className="after:border-(--border-l-color)" />
```

### 非推奨: v3 互換構文

```tsx
// ⚠️ 非推奨: 角括弧 [] と var() を使用（冗長）
<div className="bg-[var(--my-color)]" />
<div className="text-[var(--text-color)]" />
<div className="border-[var(--border-color)]" />
<div className="after:border-l-[var(--border-l-color)]" />
```

## 構文の違い

| バージョン | 構文 | 説明 |
|-----------|------|------|
| v4（推奨） | `bg-(--my-color)` | 簡潔構文。`var()` を自動的にラップ |
| v3（非推奨） | `bg-[var(--my-color)]` | 冗長。v4でも動作するが推奨しない |

## レビュー時の注意

- `[var(--` を見つけた場合は、`(--` への変更を提案してください
- v4構文 `(--variable)` は公式にサポートされている正しい構文です
- 参考: [Tailwind CSS v4 公式ドキュメント](https://tailwindcss.com/docs/adding-custom-styles)
