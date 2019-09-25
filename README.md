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

4a84d2c7e6a344d2a431a6b7cc08725a

