# Java Spring Notes
Spring Notes for Personal Use

## Import Notes

`import Java.utils.Optional;`

`import org.springframework.web.bind.annotation.RequestMapping;`

`import org.springframework.web.bind.annotation.ResponseBody;`

`import org.springframework.ui.Model;`

`import org.springframework.web.bind.annotation.PathVariable;`

`import org.springframework.web.bind.annotation.RequestParam;`

## Using methods
`@RequestMapping(value = "/addStudent", method = RequestMethod.POST)`

Or with import

`import static org.springframework.web.bind.annotation.RequestMethod.*;`

## Using Regex in RequestMapping
`@Request Mapping(value = “user/{userId:[a-z]+}”, method = GET`

## Using Optional in PathVariable
	@RequestMapping(value = {"/persons", "/persons/{id}"})

	@ResponseBody

	List<Person> getPersonInfo(

	@PathVariable(value="id") Optional<Long> id) {

		if (id.isPresent()) {
		List<Person> person = jdbcTemplate.query(("select * from persons where \"PERSONID\" = " + String.valueOf(id.get())), BeanPropertyRowMapper.newInstance(Person.class));
		return person;
		} else {
		    return  java.util.Collections.emptyList();
		}

## @RequestParam

	foo(
		@RequestParam(
		value = "userID",
		required=true,
		defaultValue = "0")
    int userId)


