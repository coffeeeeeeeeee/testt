func init() { // 回调函数
	audit.Attach(model.AuditTypeRiskControl, func(jid, op string) error {
		// 这里返回的op表示审核结果操作内容，有 approve 和 reject 两种
		log.Infof("audit notify of risk control was received, operation is %s", op)
		switch op {
		case model.OperationApprove:
			return approveAuditOfScheme(jid)
		case model.OperationReject:
			return rejectAuditOfScheme(jid)
		}
		return nil
	})
	log.Info("notify task of risk control audit was registered")
}



4fec873246a1488b5a68bd1928b9a730

7909254253415057

 HttpClient httpclient = HttpClients.createDefault();

        try
        {
            URIBuilder builder = new URIBuilder("https://sandbox.api.payme.hsbc.com.hk/oauth2/token");


            URI uri = builder.build();
            HttpPost request = new HttpPost(uri);
            request.setHeader("Content-Type", "");
            request.setHeader("Accept", "");
            request.setHeader("Content-Type", "application/x-www-form-urlencoded");
            request.setHeader("api-version", "0.11");


            // Request body
            StringEntity reqEntity = new StringEntity("{body}");
            request.setEntity(reqEntity);

            HttpResponse response = httpclient.execute(request);
            HttpEntity entity = response.getEntity();

            if (entity != null) 
            {
                System.out.println(EntityUtils.toString(entity));
            }

