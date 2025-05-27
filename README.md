# Build and Push to ECR Action

這個 GitHub Action 用於打包 Docker 映像並推送到 Amazon ECR。

## 輸入參數

- `role-to-assume`: AWS role to assume（必填）
- `ecr-repository`: ECR repository name（必填）
- `image-tag`: Image tag（必填）

## 使用方式

```yaml
- name: Build and Push to ECR
  uses: kwlai0927/action-ecr-push@main
  with:
    role-to-assume: ${{ inputs.role-to-assume }}
    ecr-repository: llm-embedding
    image-tag: ${{ needs.version.outputs.version }}
```

## 注意事項

- 請確保已設定 AWS 相關的 secrets 或 role。
- 此 action 會自動在 ECR registry 前加上 `kwlai0927/` 前綴。
