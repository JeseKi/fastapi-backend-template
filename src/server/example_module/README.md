# 模块：example_module（模板版）

## 公开接口
- GET `/api/example/ping`
- POST `/api/example/items`
- GET `/api/example/items/{item_id}`

## 业务定位
- 作为最小示例模块，演示一个简单的实体 `Item` 的创建与查询。

## 数据流
- 路由 -> 依赖注入 `get_db` -> `asyncio.to_thread` 包裹同步 ORM -> SQLAlchemy -> SQLite

## 测试结构
- `test_example_router.py` - 路由层测试（API接口测试）
- `test_example_service.py` - 服务层测试（业务逻辑测试）
- `test_example_dao.py` - 数据访问层测试（数据库操作测试）

## 用法示例（curl）
```bash
curl http://localhost:8000/api/example/ping

curl -X POST http://localhost:8000/api/example/items \
  -H 'Content-Type: application/json' \
  -d '{"name":"hello"}'
```
