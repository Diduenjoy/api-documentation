# New AnswerSet Callback

You can assign to any survey a callback url, that will be called for each new answer_set completed.

Diduenjoy will `POST` the same content as `http://api.diduenjoy.com/api/v1/answer_sets/:answer_set_id?include=client,choices` to the given callback.