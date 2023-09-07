---
title: "RCE Upload CSV"
date: 2023-09-07T13:33:53+07:00
draft: false
tags: 
- bugbounty
---
# Abstraksi
Bug ini memungkinkan attacker untuk mengupload file backdoor. Bug ini muncul karena tidak ada filtering type file yang diupload sehingga memungkinkan attacker untuk mengupload file backdoor berekstensi *.php*.

    <div class="col-12 pb-2">
    	<div class="input-group">
    			<div class="custom-file">
    				<input type="file" class="custom-file-input" name="filedata" id="exampleInputF">
    						<label class="custom-file-label" for="exampleInput">Choose file</label>
    			</div>
    	</div>
    </div>
# Impact
Remote Code Execution
# Proof of Concept:
1. Login ke https://www.redacted.com/
2. Masuk ke menu *Upload data pelanggan*
3. Klik *Choose file* dan pilih file *.csv*
4. Intercept dengan Burp Suite dan klik *Upload*
5. Ubah ektensi menjadi *.php*, kemudian forward request
# Timeline
- **Report:** 10/08/2023
- **Response:** 10/08/2023
- **Rewards:** -

Demikian writeup yang tidak lengkap ini.

Regards,

**Bayu**