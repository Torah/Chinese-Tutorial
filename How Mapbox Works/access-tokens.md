---
title: Access tokens
description: Learn how access tokens work and how to create and manage your access tokens.
image: /img/narrative/access-token.svg
topics:
  - access tokens
prependJs:
  - "import ChevronousText from '@mapbox/mr-ui/chevronous-text';"
contentType: guide
---
您需要获取[access token](/help/glossary/access-token)（访问令牌）以使用Mapbox的各种工具、API、SDK。Mapbox利用access token将API请求和您的账号联系在一起。用户可以在[access token页](https://account.mapbox.com/access-tokens)或用[Mapbox Tokens API](https://docs.mapbox.com/api/accounts/#tokens)编程查找、新建、以及删除已有的access token。
To use any of Mapbox's tools, APIs, or SDKs, you'll need a Mapbox [access token](/help/glossary/access-token). Mapbox uses access tokens to associate API requests with your account. You can find your access tokens, create new ones, or delete existing ones on your [Access Tokens page](https://account.mapbox.com/access-tokens)  or programmatically using the [Mapbox Tokens API](https://docs.mapbox.com/api/accounts/#tokens).

## Access token是如运作的
## How access tokens work

### 范围
### Scopes

您所创建的每一个access token都会有一组许可证允许你向Mapbox API发起特定类型的请求——它们被称为 **scopes（范围）**。有些Mapbox API只接受包含特定token和scope的请求。创建access token的时候，您可以选择给token增添额外的[公共或私有范围](/help/glossary/access-token)。如果您选择添加任何保密的scope，则只有一次机会浏览token。
Each access token you create will have a set of permissions that allow you to make certain types of requests to Mapbox APIs -- these are called **scopes**. Some Mapbox APIs only accept requests that include tokens with a particular scope. When creating an access token, you will have the option to add additional [public or private scopes](/help/glossary/access-token) to your token. If you choose to add any secret scopes to your token, you will have only one chance to view the token.

在选择scope的时候应考虑清楚使用token的计划。**为了保护您的账号和数据，如无必要请不要授权token过多的scope。**例如，如果您要创建一个token以通过 [Mapbox Uploads API](https://docs.mapbox.com/api/maps/#uploads)向Mapbox上传数据，请确保选中`uploads:write`和`uploads:read`这两个scope。如果要在网络端或移动端应用中显示地图，您应该另行创建一个不包含私有的上传相关的scopen而包含公有的`styles:read`和`fonts:read`的 _separate_ 访问token。
When choosing scopes, consider what you plan to do with the token. **To protect your account and your data, do not grant more scopes than necessary to each token**. For example, if you are creating a token to upload data to Mapbox with the [Mapbox Uploads API](https://docs.mapbox.com/api/maps/#uploads), you will want to make sure you select the `uploads:write` and `uploads:read` scopes. To display a map in a web or mobile application, you should create a _separate_ access token that does not include the private uploads-related scopes, but does include the public `styles:read` and `fonts:read` scopes.

我们的[API文档](https://docs.mapbox.com/api/)列出了每种 Mapbox API所需要的scope。**请参考[账号文档](/help/account/tokens/)以了解可选择的scope。**
Our [API documentation](https://docs.mapbox.com/api/) lists the scopes required for each Mapbox API. **For a complete list of available scopes see the [Account documentation](/help/account/tokens/).**


### URL限制
### URL restrictions

您可以通过增加URL限制（清单）来使access token更加安全。当您给token增加URL限制的时候，该token将只回应来自您列出的URL的请求。没有限制的token将回应来自任何URL地址的请求。
You can make your access tokens more secure by adding URL restrictions. When you add a URL restriction to a token, that token will only work for requests that originate from the URLs you specify. Tokens without restrictions will work for requests originating from any URL.

**请参考[账号文档](/help/account/tokens/)以了解关于使用URL限制的要求及细节。**
**For more information on requirements and details for implementing URL restrictions, see the [Account documentation](/help/account/tokens/).**


### Token轮换
### Token rotation

任何您包含在网页里的公共[access token](/help/glossary/access-token)都将对所有查询者可见。当您怀疑有人将它用于不正当用途的时候应当删除access token并进行轮换。保密的token应当只限用于对用户不可见的地方。
Any public [access tokens](/help/glossary/access-token) you include in webpage will be visible to anyone who makes an effort to look for it. Access tokens can be deleted and rotated at any time if you suspect misuse. Secret tokens should only be used in places where they will not be visible to your users.

您可以创建无数个access token。如果您想要进行token轮换，您需要[创建一个新的access token](#creating-and-managing-access-tokens)，把它替换到项目中，并移除原先的token。未被缓存的请求将立即失效。已缓存的请求将保存（生存周期）至一个小时以后。
You can create as many access tokens as you want. To rotate, [create a new access token](#creating-and-managing-access-tokens), replace it in a project, and then remove the old token. Invalidation for uncached requests will happen immediately. Cached requests can take up to an hour.


## 创建和管理access token
## Creating and managing 访问 tokens

有两种选择可以创建和管理Mapbox 访问 token：使用UI在您Mapbox账户的token页来管理tokens，或者通过Tokens API以编程的方式创建、读取和更新tokens。
There are two options for creating and managing Mapbox access tokens: use the Tokens page in your Mapbox Account to manage tokens using a UI or use the Tokens API to create, read, and update tokens programmatically.  

### Mapbox账号界面
### Mapbox Account Dashboard

可以在您的[Access Tokens页](https://account.mapbox.com/access-tokens)创建、删除、管理access token。
Access tokens can be created, deleted, and managed on your [Access Tokens page](https://account.mapbox.com/access-tokens):

1. 点击**新建token**并给您的新token一个能有助于您记住其用途的名字。
1. Click **Create a token** and give your new token a name to help you remember its purpose.
2. 定义scopes。
2. Specify scopes.

![Example secret access token](/help/img/account/access-token-scopes.png)

3. 点击**创建token**以创建新的token。您将被提示需要重新输入密码。
3. Click **Create token** to create the token. You may be prompted to re-enter your password.
4. 创建成功！您的新token将会出现在您的token列表的最上方。
4. Success! Your new token will appear at the top of your list of tokens.

您可以点击任意token的名字以查看其scopes，如果是公共token，您可以看到其本身。
You can click on the name of any token to see the scopes it covers and, if the token is public, you can see the token itself.

如果您创建了一个私密的访问token，您将只能在账户面板上看到其一次——请确保将其保存在一个安全的地方（类似于密码管家）以防之后需要用到。
If you created a secret access token, you will only be able to see the token in your account dashboard once - be sure to store it somewhere safe (like a password manager) if you need to access it later.

![Example secret access token](/help/img/account/example-access-token.png)


### Mapbox Tokens API
### Mapbox Tokens API

通过[Mapbox Tokens API](https://docs.mapbox.com/api/accounts/#tokens)，您可以创建、读取、更新您的access token。如果要使用这个API创建另外的token，您需要首先创建一个含有`tokens:write` 范围以及您想增加的其他范围的初始token。您可以在您的[Access Tokens页](https://account.mapbox.com/access-tokens)创建这个初始token，并点击**新建token**。请参考[API文档页](https://docs.mapbox.com/api/)阅读关于Tokens API的更多内容。
With the [Mapbox Tokens API](https://docs.mapbox.com/api/accounts/#tokens) you can create, read, and update your access tokens. To create additional tokens using this API you will first need to create an initial token with the `tokens:write` scope and any scopes you want to add to the created token. To create this initial token visit your [Access Tokens page](https://account.mapbox.com/access-tokens), and click **Create a token**. Read more about the Tokens API on our [API documentation page](https://docs.mapbox.com/api/).
