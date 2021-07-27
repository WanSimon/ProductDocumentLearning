# B端产品权限设计


### 2. 权限模型

#### 2.1 ACL模型
- 访问控制列表，Access Control List


#### 2.2 DAC模型
- 自主访问控制，Discretionary Access Control



#### 2.3 MAC模型
- 强制访问控制，Mandatory Access Control



#### 2.4 RBAC模型
- 基于角色的访问控制，Role-Based Access Control
- RBAC 认为授权实际上是处理 ``` what ``` 、```how``` 、```who```三元组之间的关系，也就是```who```对``` what ```进行```how```的操作，也就是"主体"对"客体"的操作。  
  ```who```:是权限的拥有者或主体（如User、Role
  ）


- 在主体和权限之间引入“角色”概念，“角色”解耦了主体和权限之间的关系。
  - RBAC0：是RBAC的核心思想
  - RBAC1：是把RBAC的角色分层模型
  - RBAC2：增加了RBAC的约束模型
  - RBAC3：其实是RBAC2 + RBAC1



- 用户管理
  
  - 用户基本信息维护
  - 用户角色分配

- 角色管理
  - 角色信息维护
  - 角色资源授权
  - 角色权限认证
  
- 资源管理
  
  - 资源信息维护



####  2.5 ABAC模型

- 基于属性的访问控制，Attribute-Based Access Control