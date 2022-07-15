## `Passo a Passo Completo Resumido`
___


```javascript
const request = require("supertest");
const app = require("../app");


let elementId;

describe("API Test", () => {
    // agrupa vários testes
    // testar primeiro a rota GET

    test("GET /users/all", (done) => {
        request(app) // aqui acontece a conexão
            .get("/users/all")
            .expect(200)
            .expect((res) => {
                expect(res.body.length).not.toBe(0);
            })
            .end((err, res) => {
                if(err) return done(err);
                return done();
            })
    });

    test("POST /users/create", (done) => {
        request(app)
            .post("/users/create")
            .expect("Content-Type", /json/)
            .send({
                name: "Paula",
                email: "paula@gmail.com",
                password: "senhamuitodificil"
            })
            .expect(201)
            .end((err, res) => {
                if(err) return done(err);               
                elementId = res.body.savedUser._id;                
                return done();
            })
    });

    test("PATCH /users/update/:id", (done) => {
        request(app)
        .patch(`/users/update/${elementId}`)
        .expect("Content-Type", /json/)
        .send({
            name: "Paula Atualizado",
            email: "paulaatualizado@gmail.com"
        })
        .expect(200)
        .expect((res) => {
            expect(res.body.savedUser._id).toBe(elementId);
            expect(res.body.savedUser.name).toBe("Paula Atualizado");
            expect(res.body.savedUser.email).toBe("paulaatualizado@gmail.com");
        })
        .end((err, res) => {
            if(err) return done(err);
            return done();
        });
    });

    test("DELETE /users/delete/:id", (done) => {
        request(app)
          .delete(`/users/delete/${elementId}`)
          .expect("Content-Type", /json/)
          .expect(200)
          .expect((res) => {
            console.log(res.body)
            expect(res.body.userFound.email).toBe("paulaatualizado@email.com");
          })
          .end((err, res) => {
            if (err) return done(err);
            return done();
          });
      });

});

```