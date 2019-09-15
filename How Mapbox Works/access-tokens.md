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

您所创造的每一个access token都会有一系列对于可使用Mapbox API进行的请求的许可——这些被称为 **scopes（范围）**。有些Mapbox API只接受包含特定范围的token的请求。创建access token的时候，您可以选择给token增添额外的[公共或私有范围](/help/glossary/access-token)。如果您选择增添秘密范围，则只可以浏览一次token。
Each access token you create will have a set of permissions that allow you to make certain types of requests to Mapbox APIs -- these are called **scopes**. Some Mapbox APIs only accept requests that include tokens with a particular scope. When creating an access token, you will have the option to add additional [public or private scopes](/help/glossary/access-token) to your token. If you choose to add any secret scopes to your token, you will have only one chance to view the token.

在选择token范围的时候应考虑想要使用token达成的目的。**为了保护您的账号和数据，请不要给token过多的许可范围。**例如，如果您要创建一个token以使用[Mapbox Uploads API](https://docs.mapbox.com/api/maps/#uploads)向Mapbox上传数据，请确保选中`uploads:write`和`uploads:read`这两个范围。如果要在网络端或移动端应用中显示地图，您应该另创建一个不包含与私有数据上传相关的范围而包含公共范围中`styles:read`和`fonts:read`的_分别的_access token。
When choosing scopes, consider what you plan to do with the token. **To protect your account and your data, do not grant more scopes than necessary to each token**. For example, if you are creating a token to upload data to Mapbox with the [Mapbox Uploads API](https://docs.mapbox.com/api/maps/#uploads), you will want to make sure you select the `uploads:write` and `uploads:read` scopes. To display a map in a web or mobile application, you should create a _separate_ access token that does not include the private uploads-related scopes, but does include the public `styles:read` and `fonts:read` scopes.

我们的[API文档](https://docs.mapbox.com/api/)列出了每种 Mapbox API所需要的范围。**请参考[账号文档](/help/account/tokens/)以了解可选择的范围。**
Our [API documentation](https://docs.mapbox.com/api/) lists the scopes required for each Mapbox API. **For a complete list of available scopes see the [Account documentation](/help/account/tokens/).**


### URL限制
### URL restrictions

您可以通过增加URL限制来使access token更加安全。当您给token增加URL限制的时候，该token将只回应来自您列出的URL的请求。没有限制的token将回应来自任何URL的请求。
You can make your access tokens more secure by adding URL restrictions. When you add a URL restriction to a token, that token will only work for requests that originate from the URLs you specify. Tokens without restrictions will work for requests originating from any URL.

**请参考[账号文档](/help/account/tokens/)以了解使用URL限制的要求及细节。**
**For more information on requirements and details for implementing URL restrictions, see the [Account documentation](/help/account/tokens/).**


### Token轮换
### Token rotation

任何您包含在网页里的公共[access token](/help/glossary/access-token)都对每个查找它的人可显示。当您怀疑有人将它用于不正当用途的时候应当删除access token并进行轮换。秘密token应只被用于不会被您的用户看到的地方。
Any public [access tokens](/help/glossary/access-token) you include in webpage will be visible to anyone who makes an effort to look for it. Access tokens can be deleted and rotated at any time if you suspect misuse. Secret tokens should only be used in places where they will not be visible to your users.

您可以创建无数个access token。如果您想要进行token轮换，您需要[创建一个新的access token](#creating-and-managing-access-tokens)，把它替换到项目中，再移除原有的token。未缓存请求将立即被作废。已缓存的请求将花多至一个小时被作废。
You can create as many access tokens as you want. To rotate, [create a new access token](#creating-and-managing-access-tokens), replace it in a project, and then remove the old token. Invalidation for uncached requests will happen immediately. Cached requests can take up to an hour.


## 创建和管理access token
## Creating and managing access tokens

创建和管理Mapbox access token有两个选项：在您的Mapbox账号token页使用用户界面或者通过Tokens API以编程的方式创建、读取、更新token。
There are two options for creating and managing Mapbox access tokens: use the Tokens page in your Mapbox Account to manage tokens using a UI or use the Tokens API to create, read, and update tokens programmatically.  

### Mapbox账号界面
### Mapbox Account Dashboard

您可以在您的[Access Tokens页](https://account.mapbox.com/access-tokens)创建、删除、管理access token。
Access tokens can be created, deleted, and managed on your [Access Tokens page](https://account.mapbox.com/access-tokens):

1. 点击**新建token**并赋予它一个能帮助您记住其用途的名字。
1. Click **Create a token** and give your new token a name to help you remember its purpose.
2. 明确范围。
2. Specify scopes.

![Example secret access token](/help/img/account/access-token-scopes.png)

3. 点击**创建token**以创建新的token。您将被提示需要重新输入密码。
3. Click **Create token** to create the token. You may be prompted to re-enter your password.
4. 创建成功！您的新token将会出现在您的token列表的最上方。
4. Success! Your new token will appear at the top of your list of tokens.

您可以点击任意token的名字以查看其范围，如果是公共token，您可以看到其本身。
You can click on the name of any token to see the scopes it covers and, if the token is public, you can see the token itself.

如果您创建了一个秘密access token，您将只能在账户界面上看到一次——请确保将其保存在一个安全的地方（类似于密码管家）以防之后需要用到。
If you created a secret access token, you will only be able to see the token in your account dashboard once - be sure to store it somewhere safe (like a password manager) if you need to access it later.

![Example secret access token](/help/img/account/example-access-token.png)


### Mapbox Tokens API
### Mapbox Tokens API

通过[Mapbox Tokens API](https://docs.mapbox.com/api/accounts/#tokens)，您可以创建、读取、更新您的access token。如果要使用这个API创建另外的token，您需要首先创建一个含有`tokens:write` 范围以及您想增加的其他范围的初始token。您可以在您的[Access Tokens页](https://account.mapbox.com/access-tokens)创建这个初始token，并点击**新建token**。请参考[API文档页](https://docs.mapbox.com/api/)阅读关于Tokens API的更多内容。
With the [Mapbox Tokens API](https://docs.mapbox.com/api/accounts/#tokens) you can create, read, and update your access tokens. To create additional tokens using this API you will first need to create an initial token with the `tokens:write` scope and any scopes you want to add to the created token. To create this initial token visit your [Access Tokens page](https://account.mapbox.com/access-tokens), and click **Create a token**. Read more about the Tokens API on our [API documentation page](https://docs.mapbox.com/api/).
