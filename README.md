# java-persiapan






package gov.dukcapil.web.apps.siakApp.business.dafduk.rentan;

import gov.dukcapil.web.apps.siakApp.business.SubVerticalSiakAppBusiness;
import gov.dukcapil.web.libs.helper.Dukcapil;
import io.vertx.core.Vertx;
import io.vertx.core.json.JsonObject;
import io.vertx.ext.web.Router;
import io.vertx.ext.web.RoutingContext;

public class skot  extends SubVerticalSiakAppBusiness {
	
	public skot(Vertx vertx) {
		super(vertx);

	}
	
	public void getRouter(Router router) {
		

		router.route(Dukcapil.URL_TEMPAT_PENDATAAN).handler(context->{
			context.put(Dukcapil.REQ_STARTTIME, System.currentTimeMillis());
			procTempatPendataanAdd(context);
		});

		
	}
	

	private void procTempatPendataanAdd(RoutingContext context) {

		
//		responseBody = new JsonObject();
//		final JsonObject requestBody =new JsonObject(context.getBodyAsString());
//		final JsonObject jsonReqColumn =requestBody.getJsonObject(Dukcapil.KEY_REQ_TABLE);
//		
//		responseBody = new JsonObject();
//		responseClientSuccess(context, responseBody);	
		
		final JsonObject principal = context.user().principal();
		
		responseBody =new JsonObject();
		
		responseClientSuccess(context, responseBody);
		

		responseClientError(context, responseBody);

	
	
		
		
	}

}
