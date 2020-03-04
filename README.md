# json-serialize

Gson gson = new Gson();
		
		//F o1 = gson.fromJson(gson.toJson(r.getDataList().get(0)), new TypeToken<F>(){}.getType());
		//Object o = o1.getData();
		//JsonElement j = gson.toJsonTree(o);
		JsonElement j = gson.toJsonTree(r.getDataList().get(0).getData());
		if (j instanceof JsonArray) {
			System.out.println(j.getAsJsonArray().get(0));
			List<F> f = gson.fromJson(j.getAsJsonArray(), new TypeToken<List<F>>(){}.getType());
			System.out.println(f.get(0).getA());
		} else if (j instanceof JsonPrimitive) {
			System.out.println("prim");
		} else if (j instanceof JsonObject) {
			System.out.println(j.getAsJsonObject().get("ketan"));
		} else if (j instanceof JsonNull) {
			System.out.println("who am i ");
		}
