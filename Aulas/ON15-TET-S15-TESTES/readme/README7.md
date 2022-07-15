## `Passo a Passo Teste da Rota DELETE`
___



#### O DELETE não muda muita coisa:
```javascript
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
```