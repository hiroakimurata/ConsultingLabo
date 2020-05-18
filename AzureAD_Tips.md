# Azure AD Operation

- PRT and Single Sign On
	* [What is a Primary Refresh Token? (Microsoft Docs)](https://docs.microsoft.com/en-us/azure/active-directory/devices/concept-primary-refresh-token)
	* [Information included in PRT (Japanese)](https://jpazureid.github.io/blog/azure-active-directory/what-to-do-errorcode-700003/)
- PRT enables SSO for Password, MFA
	* [Azure MFA Timing (Japanese)](https://jpazureid.github.io/blog/azure-active-directory/azure-mfa-timing/)
	* Check how to show it when you choose login account in the above link

- Password management for Synced ID at Hybrid Identity

* EnforceCloudPasswordPolicyForPasswordSyncedUsers feature - Public Preview
	* Try this feature if you would like force Azure AD users to comply with your Azure AD password expiration policy
	* You can switch ON or OFF the password expiration manually by running the following command.
		> **ON**

		> 'Set-AzureADUser -ObjectID <User ID> -PasswordPolicies "DisablePasswordExpiration" '
		
		> **OFF**
		
		> 'Set-AzureADUser -ObjectID <User ID> -PasswordPolicies "None" '
		
		* [Set or check the password policies by using PowerShell](https://docs.microsoft.com/en-us/azure/active-directory/authentication/concept-sspr-policy)
		* [How password hash synchronization works](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization#how-password-hash-synchronization-works)
	
- シングルテナントマルチフォレストで条件付きアクセスを使いたい場合

* デバイス登録の前提条件

	* ドメイン参加済デバイス

	* 準拠済みデバイス（Intuneポリシーにより）

	* Write Backが必要？

		* 必要ではない。

		* Windows Hello for Business の証明書ベースの方式では必要（鍵ベースであれば問題ない）

* デバイス認証

	* 条件付きアクセス

- フォレスト構成

* シングルフォレスト

	* 新たにフォレスト作成してこちらのドメインに参加する

	* IDプロビジョニングが必要

	* デバイスのドメイン参加方法は今までの運用を踏襲した方がよいが、以下のケースが多いと思われる

		* オブジェクトを先に作っておいて後でユーザーにドメイン参加させる(手動またはスクリプト)

* マルチフォレスト

	* そのままのフォレストを使う（US・日本のそれぞれの国で統合した方がよい場合もある）

		* ADFSを利用しない場合はPHS or PTA の選択になる。各フォレストでは選択できずテナント一律で選択することになる。

